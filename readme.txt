筛查证据采集与回放服务

该项目用于采集筛查业务中的结构化证据，保存请求、解析和判定过程，并支持使用本地样例重放采集结果，方便核对去重、字段清洗和异常恢复行为。演示命令读取 fixtures/demo.json，并将处理状态写入本地 SQLite 数据库。

测试：python3 -m unittest discover -s tests/evidence_replay -p 'test_*.py'
构建：python3 -m compileall -q screening_evidence_crawler
验收：python3 -m screening_evidence_crawler.operator.crawl_cli fixtures/demo.json --db /tmp/screening_evidence_crawler-acceptance.sqlite3
