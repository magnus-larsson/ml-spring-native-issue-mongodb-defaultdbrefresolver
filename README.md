Build and run tests:

```
./gradlew build --no-daemon
```

Build native image:

```
./gradlew bootBuildImage --no-daemon
```

Gives the error:

```
[creator]     Error: Cannot find org.springframework.data.mongodb.core.convert.DefaultDbRefResolver.createLazyLoadingProxy, 
org.springframework.data.mongodb.core.convert.DefaultDbRefResolver can not be loaded, 
due to com/mongodb/client/MongoCollection not being available in the classpath. 
Are you missing a dependency in your classpath?
```

Rename `microservices/product-service/src/main/java/com/mongodb/client/MongoCollectionDisabled.java` 
to `microservices/product-service/src/main/java/com/mongodb/client/MongoCollection.java` and the native image can be built

