# 📜 Kafka Cheatsheet (Docker)

Цей документ містить основні команди для роботи з Apache Kafka, запущеною в Docker-контейнері.

## 1. Доступ до середовища

Вхід у контейнер Kafka для виконання CLI команд:

```bash
docker exec -it kafka bash
```

## 2. Перевірка статусу брокера

```bash
kafka-topics \
  --bootstrap-server kafka:29092 \
  --list
```

## 3. Створення топіків

```bash
kafka-topics \
  --bootstrap-server kafka:29092 \
  --create \
  --topic router.input \
  --partitions 3 \
  --replication-factor 1
```

## 4. Перевірка конфігурації топіка

```bash
kafka-topics \
  --bootstrap-server kafka:29092 \
  --describe \
  --topic router.input
```

## 5. Відправка повідомлень (Producer)

```bash
kafka-console-producer \
  --bootstrap-server kafka:29092 \
  --topic router.input
```

## 6. Читання повідомлень (Consumer)

```bash
kafka-console-consumer \
  --bootstrap-server kafka:29092 \
  --topic router.input \
  --from-beginning
```