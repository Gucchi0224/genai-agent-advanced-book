# Docker環境でのコマンド
.PHONY: docker.up
docker.up:
	@docker compose up -d

.PHONY: docker.down
docker.down:
	@docker compose down

.PHONY: docker.build
docker.build:
	@docker compose build

.PHONY: docker.logs
docker.logs:
	@docker compose logs -f app

.PHONY: docker.restart
docker.restart:
	@docker compose restart app

.PHONY: docker.shell
docker.shell:
	@docker compose exec app /bin/bash

# スクリプト実行用コマンド（Docker環境）
.PHONY: docker.run.01
docker.run.01:
	@docker compose exec app uv run python scripts/01_e2b_sandbox.py

.PHONY: docker.run.02
docker.run.02:
	@docker compose exec app uv run python scripts/02_jinja_template.py

.PHONY: docker.run.03
docker.run.03:
	@docker compose exec app uv run python scripts/03_describe_dataframe.py

.PHONY: docker.run.04
docker.run.04:
	@docker compose exec app uv run python scripts/04_generate_profile.py

.PHONY: docker.run.05
docker.run.05:
	@docker compose exec app uv run python scripts/05_generate_code.py

.PHONY: docker.run.06
docker.run.06:
	@docker compose exec app uv run python scripts/06_execute_code.py

.PHONY: docker.run.07
docker.run.07:
	@docker compose exec app uv run python scripts/07_generate_review.py

.PHONY: docker.run.08
docker.run.08:
	@docker compose exec app uv run python scripts/08_programmer.py

.PHONY: docker.run.09
docker.run.09:
	@docker compose exec app uv run python scripts/09_generate_plan.py

.PHONY: docker.run.10
docker.run.10:
	@docker compose exec app uv run python scripts/10_execute_plan.py

.PHONY: docker.run.11
docker.run.11:
	@docker compose exec app uv run python scripts/11_generate_report.py

# ローカル環境でのコマンド（参考）
.PHONY: run.01
run.01:
	@uv run python scripts/01_e2b_sandbox.py

.PHONY: run.02
run.02:
	@uv run python scripts/02_jinja_template.py

.PHONY: run.03
run.03:
	@uv run python scripts/03_describe_dataframe.py

.PHONY: run.04
run.04:
	@uv run python scripts/04_generate_profile.py

.PHONY: run.05
run.05:
	@uv run python scripts/05_generate_code.py

.PHONY: run.06
run.06:
	@uv run python scripts/06_execute_code.py

.PHONY: run.07
run.07:
	@uv run python scripts/07_generate_review.py

.PHONY: run.08
run.08:
	@uv run python scripts/08_programmer.py

.PHONY: run.09
run.09:
	@uv run python scripts/09_generate_plan.py

.PHONY: run.10
run.10:
	@uv run python scripts/10_execute_plan.py

.PHONY: run.11
run.11:
	@uv run python scripts/11_generate_report.py
