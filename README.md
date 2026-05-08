O que faz cada pasta/ficheiro

server/

GrpcServer → arranca o servidor 
SFServiceImpl → upload, getLabels, search 
SGServiceImpl → scaling

client/ 

envia imagem 
pede resultados

storage/ 

Cloud Storage 
upload imagem 
download imagem

pubsub/ 

comunicação assíncrona 
Publisher → envia mensagens 
Subscriber → worker recebe

firestore/ 

base de dados 
guardar resultados 
queries por label/data

vision/

deteção de labelsm usa Google Vision API 

translate/ 

traduz labels(inglês → português)

worker/ 

processar o sistema 
lê Pub/Sub 
processa imagem 
chama vision + translate 
guarda no Firestore

model/ 

objetos internos (não gRPC) estrutura de dados para guardar info