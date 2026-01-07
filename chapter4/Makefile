# ローカル環境でのコマンド
.PHONY: start.engine
start.engine:
	@docker compose up -d

.PHONY: stop.engine
stop.engine:
	@docker compose down

.PHONY: create.index
create.index:
	@uv run python -m src.scripts.create_index

.PHONY: delete.index
delete.index:
	@uv run python -m src.scripts.delete_index

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

.PHONY: docker.create.index
docker.create.index:
	@docker compose exec app uv run python -m src.scripts.create_index

.PHONY: docker.delete.index
docker.delete.index:
	@docker compose exec app uv run python -m src.scripts.delete_index

.PHONY: docker.logs
docker.logs:
	@docker compose logs -f app

.PHONY: docker.restart
docker.restart:
	@docker compose restart app