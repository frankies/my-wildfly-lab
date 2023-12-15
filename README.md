
## Wildfly boot jar

https://www.mastertheboss.com/eclipse/eclipse-microservices/wildfly-bootable-jar-datasource-configuration/


- 下载样例：

```
curl -JL --output /tmp/src.zip  https://codeload.github.com/fmarchioni/mastertheboss/zip/refs/heads/master && \
  cd /tmp/ && \
  unzip src.zip -d ./wildfly/ && \
  cd - && echo "===>> Has dowload to '/tm/wildfly/'！"
```
## 直接运行

```shell
mvn install wildfly-jar:run
```

## 打包

默认编译成 `jdk11`

```shell
 mvn clean package -T2.0C  
```

## 运行

```shell
java -jar target/postgresql-bootable.jar
```

## 瘦身jar

https://docs.wildfly.org/bootablejar/#wildfly_jar_advanced_slim

- 打包
```shell
 mvn clean package -T2.0C -Pslim
```

- 运行 

```shell
java -Dmaven.repo.local=$PWD/target/repos -jar target/postgresql-bootable.jar
```

https://github.com/fmarchioni/mastertheboss/tree/master


## 利用hollow bootjar 运行

- 制作 hollow bootjar 

```bash
cd /workspaces/my-wildfly-lab/bootable-jar/hollow-jar
 mvn clean package -T2.0C
```
- 运行

```
java -jar /workspaces/my-wildfly-lab/bootable-ja
r/hollow-jar/target/default-hollow-jar-bootable.jar  --deployment=target/rest-demo.war  --install-dir=/tmp/w2
```

## Brief

Source code for tutorials on http://www.mastertheboss.com

The source code is distributed under the MIT license (https://opensource.org/licenses/MIT)

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
