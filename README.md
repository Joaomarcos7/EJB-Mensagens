# Via DOCKER
1. Baixe o projeto
2. execute na raiz do projeto: mvn install
3. execute na raiz do projeto: docker build --tag=wildfly-app .
3. execute: docker run -it wildfly-app

# Se fizer na mão, config do standalone.xml para que essa prática dê certo, é necessário colocar dentro da tag <datasources>:

```
                <xa-datasource jndi-name="java:jboss/datasources/ExampleDS" pool-name="ExampleDS" enabled="true" use-ccm="true">
                    <xa-datasource-property name="Url">
                        jdbc:h2:mem:test;DB_CLOSE_DELAY=-1;DB_CLOSE_ON_EXIT=FALSE
                    </xa-datasource-property>
                    <driver>h2</driver>
                    <xa-pool>
                        <min-pool-size>5</min-pool-size>
                        <max-pool-size>10</max-pool-size>
                        <prefill>true</prefill>
                    </xa-pool>
                    <security>
                        <user-name>sa</user-name>
                        <password>sa</password>
                    </security>
                </xa-datasource>
                <xa-datasource jndi-name="java:jboss/datasources/ExampleDS2" pool-name="ExampleDS2" enabled="true" use-ccm="true">
                    <xa-datasource-property name="Url">
                        jdbc:h2:mem:test;DB_CLOSE_DELAY=-1;DB_CLOSE_ON_EXIT=FALSE
                    </xa-datasource-property>
                    <driver>h2</driver>
                    <xa-pool>
                        <min-pool-size>5</min-pool-size>
                        <max-pool-size>10</max-pool-size>
                        <prefill>true</prefill>
                    </xa-pool>
                    <security>
                        <user-name>sa</user-name>
                        <password>sa</password>
                    </security>
                </xa-datasource>
```
