############################################
# 🗄️ Banco de Dados (Postgres)
############################################
DB_TYPE=postgresdb
DB_POSTGRESDB_HOST=n8n_postgres
DB_POSTGRESDB_PORT=5432
DB_POSTGRESDB_DATABASE=n8n
DB_POSTGRESDB_USER=postgres
DB_POSTGRESDB_PASSWORD=TDFe9kCNxQDvoBvy

############################################
# 🧰 Fila / Redis (BullMQ)
############################################
QUEUE_BULL_REDIS_HOST=n8n_redis
QUEUE_BULL_REDIS_PORT=6379
QUEUE_BULL_REDIS_PASSWORD=TDFe9kCNxQDvoBvy

############################################
# 🏃 Execuções (Queue Mode, retenção, prune)
############################################
EXECUTIONS_MODE=queue
EXECUTIONS_TIMEOUT=1800                   # 30 min por execução
EXECUTIONS_TIMEOUT_MAX=3600               # 60 min hard cap
EXECUTIONS_DATA_SAVE_ON_SUCCESS=all
EXECUTIONS_DATA_SAVE_ON_ERROR=all
EXECUTIONS_DATA_SAVE_MANUAL_EXECUTIONS=true
EXECUTIONS_DATA_PRUNE=true
EXECUTIONS_DATA_MAX_AGE=336               # horas (14 dias)
EXECUTIONS_DATA_PRUNE_HARD_DELETE_INTERVAL=15
EXECUTIONS_DATA_HARD_DELETE_BUFFER=1
EXECUTIONS_DATA_PRUNE_MAX_COUNT=10000

# Offload manual executions para os workers (recomendado em fila)
OFFLOAD_MANUAL_EXECUTIONS_TO_WORKERS=true

############################################
# 📈 Métricas / Prometheus
############################################
N8N_METRICS=true
N8N_METRICS_INCLUDE_MESSAGE_EVENT_BUS_METRICS=true
N8N_METRICS_INCLUDE_WORKFLOW_ID_LABEL=true
N8N_METRICS_QUEUE_METRICS_INTERVAL=20

############################################
# 🌐 Hostname / URLs / Protocolo
############################################
N8N_PROTOCOL=https
N8N_HOST=main.seudominio.com.br
N8N_EDITOR_BASE_URL=https://main.seudominio.com.br/
WEBHOOK_URL=https://wh.seudominio.com.br/

############################################
# 🔐 Segurança / Runtime
############################################
N8N_ENCRYPTION_KEY=ip8fi8GcyNPfkROWYgHB21LtHdaSrSdn
N8N_DIAGNOSTICS_ENABLED=false
N8N_INSECURE_DISABLE_WEBHOOK_IFRAME_SANDBOX=true   # necessário p/ alguns embeds
N8N_COMMUNITY_PACKAGES_ALLOW_TOOL_USAGE=true
N8N_GIT_NODE_DISABLE_BARE_REPOS=true

# Runners (desligado por padrão; ligue se for usar Task Runners)
N8N_RUNNERS_ENABLED=false

# Acesso a env dentro de nós de código (false = permite)
N8N_BLOCK_ENV_ACCESS_IN_NODE=false

############################################
# 🧠 Funções / Bibliotecas permitidas (Code node)
############################################
NODE_ENV=production
NODE_FUNCTION_ALLOW_EXTERNAL=moment,lodash,moment-with-locales

############################################
# 🪵 Logs
############################################
N8N_LOG_LEVEL=debug
N8N_LOG_OUTPUT=file,console
N8N_LOG_FILE_LOCATION=/home/node/.n8n/logs/n8nmain.log

############################################
# 🕒 Timezone
############################################
GENERIC_TIMEZONE=America/Sao_Paulo
TZ=America/Sao_Paulo