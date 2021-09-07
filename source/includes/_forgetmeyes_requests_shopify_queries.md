# Query Shopify

TODO Create endpoint documentation (only call on this service), then include in listings

"/api/customers/:customerid/users/:userid/sources"

shopifyApi.POST(":sourceid/shopify/search", controller.Search)

    ctx.JSON(http.StatusOK, queryResponse)

    type QueryResponse struct {
    Models []interface{} `json:"models"`

}

func (ss *shopifyService) SearchAll(ctx context.Context, shopifySource *model.ShopifySource, shopifyQueryRequest *transport.QueryRequest) (*transport.QueryResponse, error) {
var queryResponse = new(transport.QueryResponse)
fields, values := CreateGraphqlFieldsAndValues(shopifyQueryRequest)
var graphqlFields = make([]string, len(fields))

    mongoConnection := ss.applicationContext.MongoDatabase()
    collection := mongoConnection.MongodbClient(shopifySource.UserSourceID)

    for i, s := range fields {
    	graphqlFields[i] = getFieldJsonName(s)
    }
    searchCriteria := getSearchCriteria()
    for key := range searchCriteria {
    	switch key {
    	case "customers":

    		query, err := CreateQuery(graphqlFields, values, "AND")
    		if err != nil {
    			panic(err)
    		}
    		object, err := ss.Query(ctx, shopifySource.StoreName, *shopifySource.AccessToken, GetObjectModel(key), query)
    		if err != nil {
    			panic(err)
    		}

    		queryResponse.Models = append(queryResponse.Models, object)
    		edges := object.Edges()
    		for i := 0; i < edges.EdgeLen(); i++ {
    			graphqlRequest := new(transport.GraphQLRequest)
    			node := edges.Edge(i)
    			graphqlRequest.ID = node.GetID()
    			graphqlRequest.Query = query
    			graphqlRequest.ObjectType = key
    			graphqlRequest.Fields = fields
    			graphqlRequest.Object = node
    			_, err := collection.InsertOne(ctx, graphqlRequest)
    			if err != nil {
    			}
    		}

    	default:
    		s := find(fields, values, key)
    		if s != nil {
    			for k, v := range searchCriteria[key].(map[string][]string) {
    				query, err := CreateQuery(v, s, "OR")
    				if err != nil {
    					panic(err)
    				}
    				object, err := ss.Query(ctx, shopifySource.StoreName, *shopifySource.AccessToken, GetObjectModel(k), query)
    				if err != nil {
    					panic(err)
    				}

    				queryResponse.Models = append(queryResponse.Models, object)
    				edges := object.Edges()
    				for i := 0; i < edges.EdgeLen(); i++ {
    					graphqlRequest := new(transport.GraphQLRequest)
    					node := edges.Edge(i)
    					graphqlRequest.ID = node.GetID()
    					graphqlRequest.Query = query
    					graphqlRequest.ObjectType = key
    					graphqlRequest.Fields = fields
    					graphqlRequest.Object = node
    					_, err := collection.InsertOne(ctx, graphqlRequest)
    					if err != nil {
    					}
    				}
    			}
    		}
    	}
    }

    return queryResponse, nil

}

    ctx.JSON(http.StatusOK, queryResponse)
