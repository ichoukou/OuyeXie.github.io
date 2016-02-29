# Command

How:
http://docs.mongodb.org/manual/reference/program/mongodump/
mongodump --host 192.168.0.147 --port 27018 --db docdb --collection assigneenames --username patsnap_r --password patsnap123 --out ./mongodb-dump-docdb-assigneenames-2014-11-03
http://docs.mongodb.org/manual/reference/program/mongorestore/
mongorestore --host 192.168.3.69 --port 27018 --db normalization --collection assigneenames --username normalizer --password normalizer123 /data/mongodb-dump/mongodb-dump-docdb-assigneenames-2014-11-03/docdb/assigneenames.bson
Used Command Line:
dump
mongodump --host 192.168.3.69 --port 27018 --db normalization --collection docdb_original_result_inverse --username normalizer --password normalizer123 --out ./mongodb-dump-normalization_original-docdb_original_result_inverse
mongodump --host 192.168.3.43 --port 27018 --db normalization --collection patent_original_result_inverse --username normalizer --password normalizer123 --out ./mongodb-dump-normalization_original-patent_original_result_inverse
mongodump --host 192.168.3.43 --port 27018 --db normalization --collection inventor --username normalizer --password normalizer123 --out ./mongodb-dump-normalization_original-inventor
mongodump --host 192.168.3.69 --port 27018 --db corporate --username corporate --password corporate1234 --out ./mongodb-dump-corporate mongodump --host 192.168.3.69 --port 27018 --db freebase --username huanglanxin --password huanglanxin1234 --out ./mongodb-dump-freebase
mongodump --host 192.168.3.69 --port 27018 --db university --username university --password university1234 --out ./mongodb-dump-university restore
mongorestore --host 192.168.3.44 --port 27018 --db normalization_original --collection docdb_original_result_inverse --username normalizer --password normalizer123 ./mongodb-dump-normalization_original-docdb_original_result_inverse/normalization/docdb_original_result_inverse.bson
mongorestore --host 192.168.3.44 --port 27018 --db normalization_original --collection patent_original_result_inverse --username normalizer --password normalizer123 ./mongodb-dump-normalization_original-patent_original_result_inverse/normalization/patent_original_result_inverse.bson
mongorestore --host 192.168.3.44 --port 27018 --db normalization_original --collection inventor --username normalizer --password normalizer123 ./mongodb-dump-normalization_original-inventor/normalization/inventor.bson
mongorestore --host 192.168.3.44 --port 27018 --username root --password xieouye1234 ./mongodb-dump-corporate
mongorestore --host 192.168.3.44 --port 27018 --username root --password xieouye1234 ./mongodb-dump-freebase
mongorestore --host 192.168.3.44 --port 27018 --username root --password xieouye1234 ./mongodb-dump-university