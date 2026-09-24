# 传统医药大会共同文件

本项目提供传统医药大会共同文件的服务端领域基础。当前代码包含不可重复的记录登记、本地 SQLite 保存、按编号查询、健康检查和进程内 JSON 请求入口，便于在统一事务边界上继续扩展业务流程。

## 结构

- `src/medicine_congress/domain.py` 定义基础领域记录。
- `src/medicine_congress/store.py` 管理 SQLite 表结构和事务写入。
- `src/medicine_congress/service.py` 提供登记与查询服务。
- `src/medicine_congress/api.py` 处理 JSON 请求。
- `src/medicine_congress/cli.py` 提供本地请求入口。
- `tests/` 覆盖已有的基础行为。

## 运行

运行测试：`PYTHONPATH=src python3 -m unittest discover -s tests`

检查源码：`python3 -m compileall src`

本地冒烟：`printf '%s' '{"action":"health"}' | PYTHONPATH=src python3 -m medicine_congress.cli`

项目仅使用 Python 标准库，运行期间不需要连接其他服务。
