mongo -u root -p

mongo mongodb://root:password123@172.31.92.249:27017,172.31.82.252:27017,172.31.85.231:27017/?replicaSet=nam
// (non root container)
sudo chown -R 1001 ./mongodb_data

/// config tay

rs.initiate(
  {
    _id : 'rs0',
    members: [
      { _id : 0, host : "mongo1:27017" },
      { _id : 1, host : "mongo2:27017" },
      { _id : 2, host : "mongo3:27017" }
    ]
  }
)


rsconf = {
  _id: "rs0",
  members: [
    {
     _id: 0,
     host: "mongo1:27017"
    },
    {
     _id: 1,
     host: "mongo2:27017"
    },
    {
     _id: 2,
     host: "mongo3:27017"
    }
   ]
}
