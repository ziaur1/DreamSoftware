# DreamSoftware

Create Cassandra Database for My Dream project.




Client ID

gSSSoGsqFXWIIkDxgPmpNUep
 
Client Secret

Kri0HC5SnAZUoop6w6A-2,yE-NzTlitmdezl.woh_,kma3bBrlA+3m0PT.NbGnv0NkZbmo,fwJ6IsrfuHyaH_R2KoCTJl5sOamBzZ2cq7Y_urQrTDz9_IB-WHJFTRNcm

 
Token

AstraCS:gSSSoGsqFXWIIkDxgPmpNUep:1a354eef59abdcea01f2bfb937758edc7874606f4ccb11d172177fc1b0f6d896


mutation {

  game_by_genre: createTable(
  
    keyspaceName:"dream_keyspace",
    
    tableName:"game_by_genre",
    
    ifNotExists: true,
    
    partitionKeys: [
    
      { name: "genre", type: {basic: TEXT} }
      
    ]
    
    clusteringKeys: [ 
    
    
	  { name: "title", type: {basic: TEXT}, order: "ASC" },
	  
      { name: "startDate", type: {basic: TIMESTAMP }, order: "DESC" },
      
	  { name: "endDate", type: {basic: TIMESTAMP }, order: "DESC" }, 
	  
    ]
    
    values: [
    
      { name: "startRange", type: {basic: INT} },
      
      { name: "endRange", type: {basic: INT} },
      
	  { name: "winRange", type: {basic: INT} },
	  
      { name: "thumbnail", type: {basic: TEXT} }
      
    ]
    
  )
  
}


mutation {

  game_by_tiket: createTable(
  
    keyspaceName:"dream_keyspace",
    tableName:"game_by_tiket",
    ifNotExists: true,
    partitionKeys: [
    
      { name: "userid", type: {basic: TEXT} }
    ]
    clusteringKeys: [ 
    
	  { name: "buyrange", type: {basic: INT}, order: "ASC" }     
    ]
    values: [
      { name: "price", type: {basic: INT} },
      { name: "winrange", type: {basic: INT} },
	    { name: "paidprice", type: {basic: INT} }    
    ]
  )
}


mutation insertgame {

PLAY_13: insertgame_by_genre(
    value: { 
    
      genre:"PLAY_13", 
      title:"PLAY_13",
       startDate: "2021-08-16",
       endDate: "2021-08-16",
       startRange:1,
	   endRange:8,
	   winRange:0,	
	   
      thumbnail:"https://i.imgur.com/RPa4UdO.mp4"}
      ) {
    value{title}
    }
	}

