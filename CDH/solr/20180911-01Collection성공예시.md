### 성공한 예시

클라우데라 VM에서 테스트한 코드이다.


#### 인덱스 생성
solrctl instancedir --generate $HOME/test_collection_config
cp $HOME/test_collection_config/conf/solrconfig.xml.secure
solrctl instancedir --create test_collection_config $HOME/test_collection_config
solrctl collection --create test_collection -s 1 -c test_collection_config

#### 데이터 업로드
cd /usr/share/doc/solr-doc*/example/exampledocs
java -Durl=http://quickstart.cloudera:8983/solr/test_collection/update -jar post.jar *.xml
