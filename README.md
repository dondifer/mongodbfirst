# mongodbfirst
use mySocialNet
db.createCollection('Users')
db.createCollection('Posts')
db.Users.insertMany([{username:'Joony',email:'Guardrobe@hotmail.com',age:33},{username:'Nadia',email:'Coldwater@hotmail.com',age:25},{username:'Sole',email:'Blackstone@hotmail.com',age:38},{username:'Nookie',email:'Campfire@hotmail.com',age:22},{username:'Gante',email:'Mindblow@hotmail.com',age:48},{username:'Sam',email:'Steel@hotmail.com',age:45},{username:'Alex',email:'Deephole@hotmail.com',age:24},{username:'Rami',email:'Patel@hotmail.com',age:64},{username:'Tom',email:'Gunderson@hotmail.com',age:33},{username:'Leslie',email:'Redhouse@hotmail.com',age:35}])







db.Posts.insertMany([{title:'One day',body:'',username:'Joony',comments:[{username:'Leslie',body:''},{username:'Tom',body:''}]},{title:'Will',body:'',username:'Joony',comments:[{username:'Leslie',body:''},{username:'Tom',body:''}]},{title:'Live again',body:'',username:'Joony',comments:[{username:'Leslie',body:''},{username:'Tom',body:''}]},{title:'When the fall is caming',body:'',username:'Joony',comments:[{username:'Leslie',body:''},{username:'Tom',body:''}]},{title:'You never forget',body:'',username:'Joony',comments:[{username:'Leslie',body:''},{username:'Tom',body:''}]},{title:'Those memories',body:'',username:'Joony',comments:[{username:'Leslie',body:''},{username:'Tom',body:''}]},{title:'About',body:'',username:'Joony',comments:[{username:'Leslie',body:''},{username:'Tom',body:''}]},{title:'Your chilhood',body:'',username:'Joony',comments:[{username:'Leslie',body:''},{username:'Tom',body:''}]},{title:'Even better',body:'',username:'Joony',comments:[{username:'Leslie',body:''},{username:'Tom',body:''}]},{title:'easy come',body:'',username:'Joony',comments:[{username:'Leslie',body:''},{username:'Tom',body:''}]},{title:'Easy go',body:'',username:'Joony',comments:[{username:'Leslie',body:''},{username:'Tom',body:''}]},{title:'Never mind',body:'',username:'Joony',comments:[{username:'Leslie',body:''},{username:'Tom',body:''}]},{title:'about that',body:'',username:'Joony',comments:[{username:'Leslie',body:''},{username:'Tom',body:''}]},{title:'Be aware',body:'',username:'Joony',comments:[{username:'Leslie',body:''},{username:'Tom',body:''}]},{title:'Or beware',body:'',username:'Joony',comments:[{username:'Leslie',body:''},{username:'Tom',body:''}]}])

db.Posts.updateOne({ title: 'One day' },{$set:{body: "Hello everynian", username: "Sole", comments:[{username:'Leslie',body:'Hello everyone'},{username:'Tom',body:'Aloha'}]}})

db.Posts.updateOne({ title: 'One day' },{$set:{body: "Hello people of NewYork"}})

db.Posts.updateOne({ title: 'One day' },{$set:{comments: [{username:'Joony',body:'Ciao a tutti come state'},{username:'Nookie',body:'El aliento de mi gato huele a comida de gato'}]}})


db.Users.updateOne({ username: 'Joony' },{$set:{username:'Joonys',email:'calamazov@hotmail.com',age:37}})

db.Users.updateOne({ username: 'Tom' },{$set:{email:'tomytom@hotmail.com'}})

db.Users.updateOne({ username: 'Leslie' },{$set:{email:'lesliyou@hotmail.com'}})

db.Users.updateOne({ username: 'Leslie' },{$inc:{age:5}})

db.Posts.find()

db.Posts.find({username:"Joony"})

db.Users.find({age:{$gt:20}})

db.Users.find({age:{$lt:23}})

db.Users.find({$and:[{ age: { $gte: 25 } },{ age: { $lte: 30 } }]})

db.Users.find().sort({ age: 1 })

db.Users.find().sort({ age: -1 })

db.Users.find().count()

db.Posts.find().forEach(function(publicacion) {print("Título de la publicación: \"" + publicacion.title + "\"");})

db.Users.find().limit(2)

db.Posts.find({ title: { $in: ["One day","About"] } }).limit(2);

db.Users.deleteMany({age:{$gt:30}})

db.Posts.find().forEach(function(publicacion) {db.Posts.updateOne({ title: publicacion.title },{$set: {cuentaComent: publicacion.comments.length}})})

db.Posts.find({cuentaComent:{$gt:1}})
