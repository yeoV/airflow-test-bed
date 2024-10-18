# Airflow Test Bed

Airflow DAG 개발 테스트를 위한 레포지토리

- DAG 작성 시, airflow 기능을 구현하며 배우고 연습합니다.
- Pipeline 에서 필요한 개발 연습용 페이지

---
## Set local env
- python : 3.10.14
```bash
pip install -r requirements.txt
```

## Set airflow

- `Docker compose`

<https://github.com/yeoV/airflow-test-bed/tree/main/infra>

```python
docker compose up -d
```

## Project Folder Structure

```
.
├── config
├── dags
│   ├── callback
│   ├── config
│   ├── graph_simplification
│   ├── lib
│   ├── multi
│   ├── subtask_group
│   └── xcoms
├── infra
├── plugins
├── temp
└── tests
    └── lib
```

- [callback](https://github.com/yeoV/airflow-test-bed/tree/main/dags/callback)
  - callback 기능을 사용한 Task, DAG를 위한 폴더
  - `DAG callback`, `Task callback`
- [config](https://github.com/yeoV/airflow-test-bed/tree/main/dags/config)
  - Local 에서 읽은 config 파일을 검증하는 class
  - load DAG local config (pydantic)
- [graph_simplification](https://github.com/yeoV/airflow-test-bed/tree/main/dags/graph_simplification)
  - 그래프의 복잡성을 줄이기 위한 방법들을 구현한 폴더
  - Graph simplification using `EmptyOperator`
- [lib](https://github.com/yeoV/airflow-test-bed/tree/main/dags/lib)
  - 공통적으로 사용하는 Util 함수들 구현한 폴더
  - Utils function (ES client, HDFS client, Rendering Jinja2 template)
- [subtask_group](https://github.com/yeoV/airflow-test-bed/tree/main/dags/subtask_group)
  - DAG 복잡성 감소와 이식성 증대를 위한 Taskgroup 구현한 폴더
  - Create `task group`
- [xcoms](https://github.com/yeoV/airflow-test-bed/tree/main/dags/xcom)
  - Taskgroup과 Taskflow 간 데이터 공유 테스트를 위한 폴더
  - xcom using `Taskflow API.`
- Test code
  - Airflow Test 코드 작성연습
  - Test code using `Mock`
