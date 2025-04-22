# redis-lettuce-connection-factory
redis caching config using LettuceConnectionFactory

About LettuceConnectionFactory:

Connection factory creating Lettuce -based connections.
This factory creates a new LettuceConnection on each call to getConnection(). While multiple LettuceConnections share a single thread-safe native connection by default, LettuceConnection and its clustered variant are not Thread-safe and instances should not be shared across threads.
The shared native connection is never closed by LettuceConnection, therefore it is not validated by default on getConnection(). Use setValidateConnection(boolean) to change this behavior if necessary. If shareNativeConnection is true, a shared connection will be used for regular operations and a LettuceConnectionProvider will be used to select a connection for blocking and tx operations only, which should not share a connection. If native connection sharing is disabled, new (or pooled) connections will be used for all operations.
LettuceConnectionFactory should be configured using an environmental configuration and the client configuration. Lettuce supports the following environmental configurations:
RedisStandaloneConfiguration
RedisStaticMasterReplicaConfiguration
RedisSocketConfiguration
RedisSentinelConfiguration
RedisClusterConfiguration
This connection factory implements InitializingBean and SmartLifecycle for flexible lifecycle control. It must be initialized and started before you can obtain a connection. Initialization starts this bean by default. You can SmartLifecycle. stop() and restart this connection factory if needed.
