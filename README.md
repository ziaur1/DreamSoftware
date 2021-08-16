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
      { name: "startDate", type: {basic: timestamp }, order: "DESC" },
	  { name: "endDate", type: {basic: timestamp }, order: "DESC" },    
    ]
    values: [
      { name: "startRange", type: {basic: INT} },
      { name: "endRange", type: {basic: INT} },
	  { name: "winRange", type: {basic: INT} },
      { name: "thumbnail", type: {basic: TEXT} }
    ]
  )
}

