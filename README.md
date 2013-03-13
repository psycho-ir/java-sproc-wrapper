java-sproc-wrapper
==========================

Library to make PostgreSQL stored procedures(SProcs) available through simple Java "SProcService" interfaces including automatic object serialization and deserialization (using typemapper and convention-over-configuration).

Supports horizontal database sharding, advisory locking for guaranteed single node execution, configurable statement timeouts and PostgreSQL type support for enums and hstore.

Dependencies:
-------------

 * Spring compatible type mapper for deserialize/serialize: https://github.com/danielnowak/sproc-spring-mapper

How to run integration tests
----------------------------

* install local postgres cluster running on 5432 with postgres/postgres superuser
* create zalando_test database on your localhost postgres cluster
* run integration tests (JUnit tests with database access):

    mvn clean test -Pintegration-test
	
Known issues:
-------------

* PostgreSQL JDBC driver does not honor identical type names in different schemas, this may lead to issues if typemapper is used where types are present with equal name in more than one schema.

License
-------

Copyright 2012 Zalando GmbH

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
