# BLAIM Testing Data and Metrics

Generated from the local `BLAIM_Evaluator` PostgreSQL databases on 2026-05-11 14:54:16.
This file is intended as a thesis-writing evidence pack: it keeps raw keystroke arrays out of the prose body, but preserves event counts, database identifiers, model/API outputs, metrics snapshots, authentication responses, archive summaries, and submitted code. Raw event arrays remain in `test_records.request_json.keystrokeEvents` and `keystroke_archives.events_json`.

## Data Sources

- Evaluator database: `blaim_db` on local port `5436`; tables `enrollment_records`, `test_records`, `metrics_snapshots`, `auth_reruns`.
- Keystroke database: `keystroke_db` on local port `5435`; tables `user_biometrics`, `enrollment_progress`, `auth_events`, `keystroke_archives`.
- Application code inspected: `BLAIM_Evaluator/backend/db.py`, `BLAIM_Evaluator/backend/main.py`, `BLAIM_Evaluator/keystroke-service/schema.sql`, `BLAIM_Evaluator/keystroke-service/main.py`.

## Executive Summary

| metric | value |
| --- | --- |
| Evaluator enrollment records | 32 |
| Evaluator test records | 31 |
| Metric snapshots | 2 |
| Auth reruns | 1 |
| Keystroke biometric templates | 32 |
| Enrollment progress rows | 15 |
| Keystroke session archives | 34 |
| Auth timeline events | 12 |
| Distinct students/users observed | 16 |
| Genuine test records | 17 |
| Impostor test records | 7 |
| True accepts | 14 |
| False rejects / false negatives | 3 |
| True rejects | 6 |
| False accepts / false positives | 1 |
| Genuine accept rate | 0.823529 |
| False negative rate | 0.176471 |
| False positive rate | 0.142857 |
| Average verification similarity | 0.807333 |
| Average verification risk | 0.218710 |

### Latest Saved Research Snapshot

```json
{
  "tests": 28,
  "avgRisk": 0.1996274941733905,
  "records": 60,
  "assumption": "Genuine tests measure false negatives; impostor tests measure false positives.",
  "enrollments": 15,
  "avgSimilarity": 0.8003725058266095,
  "impostorTests": 5,
  "latestSession": "IT22132550-003",
  "falseNegatives": 3,
  "falsePositives": 1,
  "falseNegativeRate": 0.13043478260869565,
  "falsePositiveRate": 0.2,
  "genuineAcceptRate": 0.8695652173913043
}
```

## Enrollment Data

### Enrollment Records by Phase

| id | user | student | phase | events | snippet | code_len | seq_created | complete | created_at |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 49 | BM2214960 | Thushan Imalka | baseline | 178 | Baseline: Python Starter Function | 171 | 4 | no | 2026-05-03 23:22:18.559944 |
| 51 | BM2214960 | Thushan Imalka | stress | 169 | Stress: Timed FizzBuzz | 267 | 3 | yes | 2026-05-03 23:34:46.843217 |
| 50 | BM2214960 | Thushan Imalka | transcription | 407 | Transcription: Java Number Utils | 479 | 10 | yes | 2026-05-03 23:30:51.032453 |
| 5 | IT22069368 | Sandul Karunarathna | baseline | 186 | Baseline: Python Starter Function | 191 | 4 | yes | 2026-05-03 16:59:22.658970 |
| 6 | IT22069368 | Sandul Karunarathna | transcription | 213 | Transcription: Java Number Utils | 255 | 5 | yes | 2026-05-03 16:59:22.706083 |
| 56 | IT22075758 | Chamika Adikari | baseline | 167 | Baseline: Python Starter Function | 189 | 3 | no | 2026-05-04 15:55:35.834597 |
| 57 | IT22075758 | Chamika Adikari | transcription | 242 | Transcription: Java Number Utils | 288 | 5 | yes | 2026-05-04 15:58:58.039464 |
| 35 | IT22106124 | M.D.S.Jayasinghe | baseline | 168 | Baseline: Python Starter Function | 191 | 3 | no | 2026-05-03 17:43:13.844862 |
| 36 | IT22106124 | M.D.S.Jayasinghe | transcription | 191 | Transcription: Java Number Utils | 242 | 4 | yes | 2026-05-03 17:46:39.972500 |
| 39 | IT22132550 | Nisal Gunawardana | baseline | 190 | Baseline: JavaScript Console Program | 177 | 4 | no | 2026-05-03 18:07:58.666183 |
| 40 | IT22132550 | Nisal Gunawardana | transcription | 157 | Transcription: Java Number Utils | 213 | 3 | yes | 2026-05-03 18:10:04.603350 |
| 45 | IT22138040 | A.M.T Imalka | baseline | 164 | Baseline: Python Starter Function | 227 | 3 | no | 2026-05-03 23:05:05.448489 |
| 47 | IT22138040 | A.M.T Imalka | cognitive | 167 | Cognitive: Valid Parentheses | 392 | 3 | yes | 2026-05-03 23:07:35.951616 |
| 44 | IT22138040 | A.M.T Imalka | stress | 179 | Stress: String Reversal | 225 | 4 | no | 2026-05-03 22:56:21.684647 |
| 46 | IT22138040 | A.M.T Imalka | transcription | 161 | Transcription: Java Number Utils | 514 | 3 | yes | 2026-05-03 23:05:52.115464 |
| 41 | IT22138422 |  | baseline | 257 | Baseline: JavaScript Console Program | 218 | 6 | no | 2026-05-03 18:19:55.906120 |
| 42 | IT22138422 |  | transcription | 174 | Transcription: Java Number Utils | 209 | 3 | yes | 2026-05-03 18:26:02.138939 |
| 59 | IT22221032 | Yashodara Athapaththu | baseline | 216 | Baseline: JavaScript Console Program | 198 | 5 | no | 2026-05-04 16:12:26.409761 |
| 60 | IT22221032 | Yashodara Athapaththu | stress | 220 | Stress: Timed FizzBuzz | 278 | 5 | no | 2026-05-04 16:15:49.011010 |
| 37 | IT22251596 | Ranuga Senadeeera | baseline | 152 | Baseline: Python Starter Function | 167 | 3 | no | 2026-05-03 17:57:14.380025 |
| 38 | IT22251596 | Ranuga Senadeeera | transcription | 164 | Transcription: Java Number Utils | 206 | 3 | yes | 2026-05-03 18:01:37.824889 |
| 3 | IT22266828 | Hasintha Dilshan | baseline | 173 | Baseline: Python Starter Function | 184 | 3 | yes | 2026-05-03 16:59:22.738202 |
| 1 | IT22266828 | Hasintha Dilshan | transcription | 164 | Transcription: Java Number Utils | 205 | 3 | yes | 2026-05-03 17:38:43.383202 |
| 54 | IT22267122 | Parakrama Ekanayake | baseline | 185 | Baseline: JavaScript Console Program | 204 | 4 | no | 2026-05-04 15:33:45.044537 |
| 55 | IT22267122 | Parakrama Ekanayake | cognitive | 188 | Cognitive: Fibonacci Memoization | 250 | 4 | no | 2026-05-04 15:37:24.607217 |
| 52 | IT22277190 | Rathnayaka H M  S S | baseline | 163 | Baseline: Python Starter Function | 201 | 3 | no | 2026-05-04 00:03:38.602324 |
| 53 | IT22277190 | Rathnayaka H M  S S | cognitive | 185 | Cognitive: Fibonacci Memoization | 230 | 4 | no | 2026-05-04 00:06:46.029749 |
| 61 | IT23736382 | Thejandeera Sandeepana | baseline | 236 | Baseline: JavaScript Console Program | 254 | 5 | no | 2026-05-04 16:29:37.446026 |
| 62 | IT23736382 | Thejandeera Sandeepana | transcription | 196 | Transcription: Java Number Utils | 252 | 4 | yes | 2026-05-04 16:32:00.615097 |
| 33 | codex_probe_user | Codex Probe | baseline | 210 |  |  | 4 | no | 2026-05-03 17:34:19.103809 |
| 8 | it22081520 | Dananjaya Ariyasena | baseline | 177 | Baseline: Python Starter Function | 189 | 4 | no | 2026-05-03 16:59:22.791937 |
| 7 | it22081520 | Dananjaya Ariyasena | stress | 225 | Stress: Timed FizzBuzz | 274 | 5 | no | 2026-05-03 16:59:22.807173 |

### Keystroke Service Biometric Templates

| id | user | phase | samples | template_bytes | std_bytes | active | updated_at |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 46 | BM2214960 | baseline | 4 | 662 | 662 | yes | 2026-05-03 17:52:18.517202 |
| 48 | BM2214960 | stress | 3 | 662 | 662 | yes | 2026-05-03 18:04:46.835207 |
| 47 | BM2214960 | transcription | 10 | 662 | 662 | yes | 2026-05-03 18:00:50.980872 |
| 24 | IT22069368 | baseline | 4 | 662 | 662 | yes | 2026-05-03 11:29:22.634881 |
| 25 | IT22069368 | transcription | 5 | 662 | 662 | yes | 2026-05-03 11:29:22.697434 |
| 53 | IT22075758 | baseline | 3 | 662 | 662 | yes | 2026-05-04 10:25:35.784153 |
| 54 | IT22075758 | transcription | 5 | 662 | 662 | yes | 2026-05-04 10:28:58.024340 |
| 32 | IT22106124 | baseline | 3 | 662 | 662 | yes | 2026-05-03 12:13:13.794006 |
| 33 | IT22106124 | transcription | 4 | 662 | 662 | yes | 2026-05-03 12:16:39.919012 |
| 36 | IT22132550 | baseline | 4 | 662 | 662 | yes | 2026-05-03 12:37:58.616819 |
| 37 | IT22132550 | transcription | 3 | 662 | 662 | yes | 2026-05-03 12:40:04.598340 |
| 42 | IT22138040 | baseline | 3 | 662 | 662 | yes | 2026-05-03 17:35:05.395648 |
| 44 | IT22138040 | cognitive | 3 | 662 | 662 | yes | 2026-05-03 17:37:35.896098 |
| 41 | IT22138040 | stress | 4 | 662 | 662 | yes | 2026-05-03 17:26:21.632478 |
| 43 | IT22138040 | transcription | 3 | 662 | 662 | yes | 2026-05-03 17:35:52.056804 |
| 38 | IT22138422 | baseline | 6 | 662 | 662 | yes | 2026-05-03 12:49:55.855422 |
| 39 | IT22138422 | transcription | 3 | 662 | 662 | yes | 2026-05-03 12:56:02.124291 |
| 56 | IT22221032 | baseline | 5 | 662 | 662 | yes | 2026-05-04 10:42:26.361689 |
| 57 | IT22221032 | stress | 5 | 662 | 662 | yes | 2026-05-04 10:45:48.954993 |
| 34 | IT22251596 | baseline | 3 | 662 | 662 | yes | 2026-05-03 12:27:14.328744 |
| 35 | IT22251596 | transcription | 3 | 662 | 662 | yes | 2026-05-03 12:31:37.808141 |
| 26 | IT22266828 | baseline | 3 | 662 | 662 | yes | 2026-05-03 11:29:22.729334 |
| 27 | IT22266828 | transcription | 3 | 662 | 662 | yes | 2026-05-03 12:08:43.329402 |
| 51 | IT22267122 | baseline | 4 | 662 | 662 | yes | 2026-05-04 10:03:45.007637 |
| 52 | IT22267122 | cognitive | 4 | 662 | 662 | yes | 2026-05-04 10:07:24.556120 |
| 49 | IT22277190 | baseline | 3 | 662 | 662 | yes | 2026-05-03 18:33:38.551442 |
| 50 | IT22277190 | cognitive | 4 | 662 | 662 | yes | 2026-05-03 18:36:46.014148 |
| 58 | IT23736382 | baseline | 5 | 662 | 662 | yes | 2026-05-04 10:59:37.394734 |
| 59 | IT23736382 | transcription | 4 | 662 | 662 | yes | 2026-05-04 11:02:00.599007 |
| 30 | codex_probe_user | baseline | 4 | 662 | 662 | yes | 2026-05-03 12:04:19.057839 |
| 28 | it22081520 | baseline | 4 | 662 | 662 | yes | 2026-05-03 11:29:22.788168 |
| 29 | it22081520 | stress | 5 | 662 | 662 | yes | 2026-05-03 11:29:22.803362 |

### Enrollment Progress Rows

| user | baseline | transcription | stress | cognitive | total_sessions | complete | updated_at |
| --- | --- | --- | --- | --- | --- | --- | --- |
| BM2214960 | yes | yes | yes | no | 3 | yes | 2026-05-03 18:04:46.838956 |
| IT22069368 | yes | yes | no | no | 10 | yes | 2026-05-03 11:29:22.700695 |
| IT22075758 | yes | yes | no | no | 3 | yes | 2026-05-04 10:28:58.028591 |
| IT22106124 | yes | yes | no | no | 2 | yes | 2026-05-03 12:16:39.958449 |
| IT22132550 | yes | yes | no | no | 2 | yes | 2026-05-03 12:40:04.599508 |
| IT22138040 | yes | yes | yes | yes | 5 | yes | 2026-05-03 17:37:35.933846 |
| IT22138422 | yes | yes | no | no | 3 | yes | 2026-05-03 12:56:02.127607 |
| IT22221032 | yes | no | yes | no | 2 | no | 2026-05-04 10:45:48.994388 |
| IT22251596 | yes | yes | no | no | 2 | yes | 2026-05-03 12:31:37.812200 |
| IT22266828 | yes | yes | no | no | 10 | yes | 2026-05-03 12:08:43.368202 |
| IT22267122 | yes | no | no | yes | 2 | no | 2026-05-04 10:07:24.595330 |
| IT22277190 | yes | no | no | yes | 2 | no | 2026-05-03 18:36:46.017922 |
| IT23736382 | yes | yes | no | no | 2 | yes | 2026-05-04 11:02:00.603248 |
| codex_probe_user | yes | no | no | no | 1 | no | 2026-05-03 12:04:19.094901 |
| it22081520 | yes | no | yes | no | 10 | no | 2026-05-03 11:29:22.804349 |

### Keystroke View: User Enrollment Summary

| user_id | phases_enrolled | total_samples | enrollment_complete | total_sessions | last_updated |
| --- | --- | --- | --- | --- | --- |
| BM2214960 | 3 | 17 | yes | 3 | 2026-05-03 18:04:46.835207 |
| IT22069368 | 2 | 9 | yes | 10 | 2026-05-03 11:29:22.697434 |
| IT22075758 | 2 | 8 | yes | 3 | 2026-05-04 10:28:58.024340 |
| IT22106124 | 2 | 7 | yes | 2 | 2026-05-03 12:16:39.919012 |
| IT22132550 | 2 | 7 | yes | 2 | 2026-05-03 12:40:04.598340 |
| IT22138040 | 4 | 13 | yes | 5 | 2026-05-03 17:37:35.896098 |
| IT22138422 | 2 | 9 | yes | 3 | 2026-05-03 12:56:02.124291 |
| IT22221032 | 2 | 10 | no | 2 | 2026-05-04 10:45:48.954993 |
| IT22251596 | 2 | 6 | yes | 2 | 2026-05-03 12:31:37.808141 |
| IT22266828 | 2 | 6 | yes | 10 | 2026-05-03 12:08:43.329402 |
| IT22267122 | 2 | 8 | no | 2 | 2026-05-04 10:07:24.556120 |
| IT22277190 | 2 | 7 | no | 2 | 2026-05-03 18:36:46.014148 |
| IT23736382 | 2 | 9 | yes | 2 | 2026-05-04 11:02:00.599007 |
| codex_probe_user | 1 | 4 | no | 1 | 2026-05-03 12:04:19.057839 |
| it22081520 | 2 | 9 | no | 10 | 2026-05-03 11:29:22.803362 |

## Testing Outputs

### Per-Test Authentication, Monitoring, Identification, and Archive Outputs

| id | user | student | session | type | events | captured | archived | threshold | auth | similarity | risk | monitor | checks | identify_best | identify_conf | identify_level | outcome | created_at |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | IT22266828 | Hasintha Dilshan | IT22266828-001 | unknown | 170 | 170 | 0 | 0.700000 | yes | 0.999930 | 0.000070 | COLLECTING_DATA |  | IT22266828 | 74.745327 | MEDIUM |  | 2026-05-03 14:43:27.463375 |
| 2 | it22081520 | Dananjaya Ariyasena | it22081520-001 | unknown | 193 | 193 | 193 | 0.700000 | yes | 0.999119 | 0.000881 | AUTHENTICATED | 2 | it22081520 | 98.896503 | HIGH |  | 2026-05-03 15:53:59.819025 |
| 3 | IT22069368 | Sandul Karunarathna | IT22069368-001 | unknown | 189 | 189 | 189 | 0.700000 | yes | 0.999451 | 0.000549 | AUTHENTICATED | 2 | it22081520 | 88.685083 | HIGH |  | 2026-05-03 15:56:20.703029 |
| 4 | it22081520 | Dananjaya Ariyasena | it22081520-002 | unknown | 205 | 205 | 205 | 0.700000 | yes | 0.998001 | 0.001999 | AUTHENTICATED | 2 | IT22266828 | 58.572865 | LOW |  | 2026-05-03 15:59:30.765799 |
| 5 | IT22266828 | Hasintha Dilshan | IT22266828-002 | unknown | 175 | 175 | 175 | 0.700000 | yes | 0.998906 | 0.001094 | AUTHENTICATED | 2 | IT22266828 | 81.914479 | HIGH |  | 2026-05-03 16:31:17.330644 |
| 6 | IT22266828 | Hasintha Dilshan | IT22266828-003 | unknown | 107 | 107 | 107 | 0.700000 | yes | 0.705244 | 0.294756 | COLLECTING_DATA |  | IT22266828 | 70.524371 | MEDIUM |  | 2026-05-03 17:01:24.302909 |
| 7 | IT22266828 | Hasintha Dilshan | IT22266828-004 | unknown | 147 | 147 | 147 | 0.700000 | yes | 0.757570 | 0.242430 | COLLECTING_DATA |  | IT22266828 | 75.756955 | MEDIUM |  | 2026-05-03 17:02:53.919437 |
| 8 | IT22106124 | M.D.S.Jayasinghe | IT22106124-001 | genuine | 184 | 184 | 184 | 0.700000 | yes | 0.997419 | 0.002581 | AUTHENTICATED | 2 | IT22106124 | 99.741882 | HIGH | true accept | 2026-05-03 17:50:20.991651 |
| 9 | IT22106124 | M.D.S.Jayasinghe | IT22106124-002 | impostor | 198 | 198 | 198 | 0.700000 | no | 0.458690 | 0.541310 | REJECTED | 2 | it22081520 | 81.025040 | HIGH | true reject | 2026-05-03 17:53:33.062075 |
| 10 | IT22251596 | Ranuga Senadeeera | IT22251596-001 | genuine | 115 | 115 | 115 | 0.700000 | yes | 0.965739 | 0.034261 | COLLECTING_DATA |  | IT22251596 | 96.573877 | HIGH | true accept | 2026-05-03 18:03:32.371681 |
| 11 | IT22132550 | Nisal Gunawardana | IT22132550-001 | genuine | 117 | 117 | 117 | 0.700000 | yes | 0.940590 | 0.059410 | COLLECTING_DATA |  | IT22251596 | 95.913553 | HIGH | true accept | 2026-05-03 18:11:58.178239 |
| 12 | IT22132550 | Nisal Gunawardana | IT22132550-002 | impostor | 117 | 117 | 117 | 0.700000 | no | 0.670978 | 0.329022 | COLLECTING_DATA |  | IT22266828 | 80.200917 | HIGH | true reject | 2026-05-03 18:13:33.337001 |
| 13 | IT22138422 |  | IT22138422-001 | genuine | 119 | 119 | 119 | 0.700000 | yes | 0.986555 | 0.013445 | COLLECTING_DATA |  | IT22138422 | 98.655498 | HIGH | true accept | 2026-05-03 18:29:15.275774 |
| 14 | IT22069368 | Sandul Karunarathna | IT22069368-002 | genuine | 107 | 107 | 107 | 0.700000 | yes | 0.983017 | 0.016983 | COLLECTING_DATA |  | IT22069368 | 98.301673 | HIGH | true accept | 2026-05-03 19:03:47.217590 |
| 15 | IT22069368 | Sandul Karunarathna | IT22069368-003 | genuine | 117 | 117 | 117 | 0.700000 | no | 0.519549 | 0.480451 | COLLECTING_DATA |  | it22081520 | 88.376617 | HIGH | false reject | 2026-05-03 19:05:51.069371 |
| 16 | IT22138040 | A.M.T Imalka | IT22138040-001 | genuine | 164 | 164 | 164 | 0.700000 | no | -0.079550 | 1.079550 | REJECTED | 2 | IT22106124 | 86.393321 | HIGH | false reject | 2026-05-03 23:12:09.624030 |
| 17 | BM2214960 | Thushan Imalka | BM2214960-001 | genuine | 186 | 186 | 186 | 0.700000 | yes | 0.980424 | 0.019576 | AUTHENTICATED | 2 | BM2214960 | 98.042417 | HIGH | true accept | 2026-05-03 23:47:18.857306 |
| 18 | BM2214960def |  | BM2214960def-001 | genuine | 421 | 421 | 421 | 0.700000 | no |  | 1.000000 | ERROR |  | BM2214960 | 89.447868 | HIGH | false reject | 2026-05-03 23:55:12.147776 |
| 19 | BM2214960 | Thushan Imalka | BM2214960-002 | genuine | 421 | 421 | 421 | 0.700000 | yes | 0.894479 | 0.105521 | AUTHENTICATED | 4 | BM2214960 | 89.447868 | HIGH | true accept | 2026-05-03 23:56:45.030261 |
| 20 | IT22277190 | Rathnayaka H M  S S | IT22277190-001 | genuine | 155 | 155 | 155 | 0.700000 | yes | 0.987149 | 0.012851 | AUTHENTICATED | 2 | it22081520 | 99.060935 | HIGH | true accept | 2026-05-04 00:10:30.291695 |
| 21 | IT22266828 | Hasintha Dilshan | IT22266828-005 | genuine | 106 | 106 | 106 | 0.700000 | yes | 0.839723 | 0.160277 | COLLECTING_DATA |  | IT22266828 | 83.972341 | HIGH | true accept | 2026-05-04 15:26:49.979701 |
| 22 | IT22267122 | Parakrama Ekanayake | IT22267122-001 | genuine | 161 | 161 | 161 | 0.700000 | yes | 0.986725 | 0.013275 | AUTHENTICATED | 2 | IT22267122 | 98.672539 | HIGH | true accept | 2026-05-04 15:40:18.771150 |
| 23 | IT22267122 | Parakrama Ekanayake | IT22267122-002 | impostor | 119 | 119 | 119 | 0.700000 | no | 0.355450 | 0.644550 | COLLECTING_DATA |  | IT22266828 | 92.586768 | HIGH | true reject | 2026-05-04 15:47:07.092095 |
| 24 | IT22075758 | Chamika Adikari | IT22075758-001 | genuine | 117 | 117 | 117 | 0.700000 | yes | 0.987983 | 0.012017 | COLLECTING_DATA |  | IT22138040 | 98.827833 | HIGH | true accept | 2026-05-04 16:00:52.168594 |
| 25 | IT22075758 | Chamika Adikari | IT22075758-002 | impostor | 141 | 141 | 141 | 0.700000 | yes | 0.963656 | 0.036344 | COLLECTING_DATA |  | IT22267122 | 99.226189 | HIGH | false accept | 2026-05-04 16:04:38.177388 |
| 27 | IT22221032 | Yashodara Athapaththu | IT22221032-001 | genuine | 139 | 139 | 139 | 0.700000 | yes | 0.988210 | 0.011790 | COLLECTING_DATA |  | IT22221032 | 98.821038 | HIGH | true accept | 2026-05-04 16:18:01.699201 |
| 28 | IT23736382 | Thejandeera Sandeepana | IT23736382-001 | genuine | 105 | 105 | 105 | 0.700000 | yes | 0.914218 | 0.085782 | COLLECTING_DATA |  | IT22075758 | 98.952967 | HIGH | true accept | 2026-05-04 16:33:40.063452 |
| 31 | IT22132550 | Nisal Gunawardana | IT22132550-003 | impostor | 118 | 118 | 118 | 0.700000 | no | 0.531656 | 0.468344 | COLLECTING_DATA |  | IT22221032 | 97.390932 | HIGH | true reject | 2026-05-05 16:28:01.838254 |
| 32 | IT22138040 | A.M.T Imalka | IT22138040-002 | impostor | 145 | 145 | 145 | 0.700000 | no | 0.505985 | 0.494015 | COLLECTING_DATA |  | IT22266828 | 90.255755 | HIGH | true reject | 2026-05-06 07:39:25.981910 |
| 33 | IT22266828 | Hasintha Dilshan | IT22266828-006 | genuine | 141 | 141 | 141 | 0.700000 | yes | 0.954586 | 0.045414 | COLLECTING_DATA |  | IT22266828 | 95.458561 | HIGH | true accept | 2026-05-06 07:40:42.179212 |
| 34 | BM2214960 | Thushan Imalka | BM2214960-003 | impostor | 135 | 135 | 135 | 0.700000 | no | 0.428526 | 0.571474 | COLLECTING_DATA |  | IT22266828 | 82.602209 | HIGH | true reject | 2026-05-06 07:42:25.286466 |

### Per-Student Test Summary

| user | student | enrollment_phases | enrollment_events | tests | test_events | avg_similarity | avg_risk | false_accepts | false_rejects |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| BM2214960 | Thushan Imalka | baseline, stress, transcription | 754 | 3 | 742 | 0.767810 | 0.232190 | 0 | 0 |
| BM2214960def |  |  | 0 | 1 | 421 |  | 1.000000 | 0 | 1 |
| IT22069368 | Sandul Karunarathna | baseline, transcription | 399 | 3 | 413 | 0.834005 | 0.165995 | 0 | 1 |
| IT22075758 | Chamika Adikari | baseline, transcription | 409 | 2 | 258 | 0.975820 | 0.024180 | 1 | 0 |
| IT22106124 | M.D.S.Jayasinghe | baseline, transcription | 359 | 2 | 382 | 0.728054 | 0.271946 | 0 | 0 |
| IT22132550 | Nisal Gunawardana | baseline, transcription | 347 | 3 | 352 | 0.714408 | 0.285592 | 0 | 0 |
| IT22138040 | A.M.T Imalka | baseline, cognitive, stress, transcription | 671 | 2 | 309 | 0.213218 | 0.786782 | 0 | 1 |
| IT22138422 |  | baseline, transcription | 431 | 1 | 119 | 0.986555 | 0.013445 | 0 | 0 |
| IT22221032 | Yashodara Athapaththu | baseline, stress | 436 | 1 | 139 | 0.988210 | 0.011790 | 0 | 0 |
| IT22251596 | Ranuga Senadeeera | baseline, transcription | 316 | 1 | 115 | 0.965739 | 0.034261 | 0 | 0 |
| IT22266828 | Hasintha Dilshan | baseline, transcription | 337 | 6 | 846 | 0.875993 | 0.124007 | 0 | 0 |
| IT22267122 | Parakrama Ekanayake | baseline, cognitive | 373 | 2 | 280 | 0.671088 | 0.328912 | 0 | 0 |
| IT22277190 | Rathnayaka H M  S S | baseline, cognitive | 348 | 1 | 155 | 0.987149 | 0.012851 | 0 | 0 |
| IT23736382 | Thejandeera Sandeepana | baseline, transcription | 432 | 1 | 105 | 0.914218 | 0.085782 | 0 | 0 |
| codex_probe_user | Codex Probe | baseline | 210 | 0 | 0 |  |  | 0 | 0 |
| it22081520 | Dananjaya Ariyasena | baseline, stress | 402 | 2 | 398 | 0.998560 | 0.001440 | 0 | 0 |

### Auth Reruns

| id | test_record_id | user | session | threshold | auth | similarity | risk | created_at |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | 1 | IT22266828 | IT22266828-001 | 0.700000 | yes | 0.999930 | 0.000070 | 2026-05-03 15:19:27.664763 |

## Session Archives and Timeline Data

### Keystroke Archives

| id | user | session | assignment | events | duration_s | avg_risk | max_risk | anomalies | auth_failures | code_chars | analysis | archived_at |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | IT22266828 | IT22266828-001 |  | 0 | 0 | 0.000000 | 0.000000 | 0 | 0 | 200 | no | 2026-05-03 09:13:27.426020 |
| 2 | it22081520 | it22081520-001 |  | 193 | 0 | 0.000701 | 0.000701 | 0 | 0 | 270 | no | 2026-05-03 10:23:59.760798 |
| 3 | IT22069368 | IT22069368-001 |  | 189 | 0 | 0.000298 | 0.000298 | 0 | 0 | 270 | no | 2026-05-03 10:26:20.655394 |
| 4 | it22081520 | it22081520-002 |  | 205 | 0 | 0.000564 | 0.000564 | 0 | 0 | 186 | no | 2026-05-03 10:29:30.719629 |
| 5 | IT22266828 | IT22266828-002 |  | 175 | 0 | 0.000714 | 0.000714 | 0 | 0 | 168 | no | 2026-05-03 11:01:17.285505 |
| 6 | IT22266828 | IT22266828-003 |  | 107 | 0 | 0.000000 | 0.000000 | 0 | 0 | 121 | no | 2026-05-03 11:31:24.282833 |
| 7 | IT22266828 | IT22266828-004 |  | 147 | 0 | 0.000000 | 0.000000 | 0 | 0 | 197 | no | 2026-05-03 11:32:53.869557 |
| 8 | IT22106124 | IT22106124-001 |  | 184 | 0 | 0.010989 | 0.010989 | 0 | 0 | 270 | no | 2026-05-03 12:20:20.976031 |
| 9 | IT22106124 | IT22106124-002 |  | 198 | 0 | 0.911899 | 0.911899 | 1 | 1 | 247 | no | 2026-05-03 12:23:33.015443 |
| 10 | IT22251596 | IT22251596-001 |  | 115 | 0 | 0.000000 | 0.000000 | 0 | 0 | 137 | no | 2026-05-03 12:33:32.325957 |
| 11 | IT22132550 | IT22132550-001 |  | 117 | 0 | 0.000000 | 0.000000 | 0 | 0 | 104 | no | 2026-05-03 12:41:58.110502 |
| 12 | IT22132550 | IT22132550-002 |  | 117 | 0 | 0.000000 | 0.000000 | 0 | 0 | 161 | no | 2026-05-03 12:43:33.266319 |
| 13 | IT22138422 | IT22138422-001 |  | 119 | 0 | 0.000000 | 0.000000 | 0 | 0 | 131 | no | 2026-05-03 12:59:15.208976 |
| 14 | IT22069368 | IT22069368-002 |  | 107 | 0 | 0.000000 | 0.000000 | 0 | 0 | 137 | no | 2026-05-03 13:33:47.182720 |
| 15 | IT22069368 | IT22069368-003 |  | 117 | 0 | 0.000000 | 0.000000 | 0 | 0 | 158 | no | 2026-05-03 13:35:51.023658 |
| 16 | IT22138040 | IT22138040-001 |  | 164 | 0 | 1.254475 | 1.254475 | 1 | 1 | 281 | no | 2026-05-03 17:42:09.576389 |
| 17 | BM2214960 | BM2214960-001 |  | 186 | 0 | 0.047120 | 0.047120 | 0 | 0 | 265 | no | 2026-05-03 18:17:18.808345 |
| 18 | BM2214960def | BM2214960def-001 |  | 421 | 0 | 0.000000 | 0.000000 | 0 | 1 | 203 | no | 2026-05-03 18:25:12.092209 |
| 19 | BM2214960 | BM2214960-002 |  | 421 | 0 | 0.091405 | 0.091405 | 0 | 0 | 203 | no | 2026-05-03 18:26:44.961745 |
| 20 | IT22277190 | IT22277190-001 |  | 155 | 0 | 0.009316 | 0.009316 | 0 | 0 | 219 | no | 2026-05-03 18:40:30.249593 |
| 21 | IT22266828 | IT22266828-005 |  | 106 | 0 | 0.000000 | 0.000000 | 0 | 0 | 147 | no | 2026-05-04 09:56:49.950002 |
| 22 | IT22267122 | IT22267122-001 |  | 161 | 0 | 0.024627 | 0.024627 | 0 | 0 | 253 | no | 2026-05-04 10:10:18.721279 |
| 23 | IT22267122 | IT22267122-002 |  | 119 | 0 | 0.000000 | 0.000000 | 0 | 0 | 160 | no | 2026-05-04 10:17:07.033822 |
| 24 | IT22075758 | IT22075758-001 |  | 117 | 0 | 0.000000 | 0.000000 | 0 | 0 | 155 | no | 2026-05-04 10:30:52.096232 |
| 25 | IT22075758 | IT22075758-002 |  | 141 | 0 | 0.000000 | 0.000000 | 0 | 0 | 208 | no | 2026-05-04 10:34:38.102665 |
| 26 | IT22075758 | IT22075758-003 |  | 141 | 0 | 0.000000 | 0.000000 | 0 | 0 | 208 | no | 2026-05-04 10:34:53.069872 |
| 27 | IT22221032 | IT22221032-001 |  | 139 | 0 | 0.000000 | 0.000000 | 0 | 0 | 192 | no | 2026-05-04 10:48:01.620787 |
| 28 | IT23736382 | IT23736382-001 |  | 105 | 0 | 0.000000 | 0.000000 | 0 | 0 | 134 | no | 2026-05-04 11:03:39.989129 |
| 29 | IT23736382 | IT23736382-002 |  | 147 | 0 | 0.000000 | 0.000000 | 0 | 0 | 171 | no | 2026-05-04 11:07:16.578699 |
| 30 | IT22221032 | IT22221032-002 |  | 110 | 0 | 0.000000 | 0.000000 | 0 | 0 | 118 | no | 2026-05-05 10:53:26.227625 |
| 31 | IT22132550 | IT22132550-003 |  | 118 | 0 | 0.000000 | 0.000000 | 0 | 0 | 140 | no | 2026-05-05 10:58:01.804238 |
| 32 | IT22138040 | IT22138040-002 |  | 145 | 0 | 0.000000 | 0.000000 | 0 | 0 | 142 | no | 2026-05-06 02:09:25.954606 |
| 33 | IT22266828 | IT22266828-006 |  | 141 | 0 | 0.000000 | 0.000000 | 0 | 0 | 208 | no | 2026-05-06 02:10:42.166505 |
| 34 | BM2214960 | BM2214960-003 |  | 135 | 0 | 0.000000 | 0.000000 | 0 | 0 | 183 | no | 2026-05-06 02:12:25.275239 |

### Session Risk Summary View

| session | user | assignment | checks | avg_similarity | avg_risk | max_risk | anomalies | failures | start | end |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| BM2214960-001 | BM2214960 |  | 1 | 0.952880 | 0.047120 | 0.047120 | 0 | 0 | 2026-05-03 18:17:18.796752 | 2026-05-03 18:17:18.796752 |
| BM2214960-002 | BM2214960 |  | 1 | 0.908595 | 0.091405 | 0.091405 | 0 | 0 | 2026-05-03 18:26:44.948372 | 2026-05-03 18:26:44.948372 |
| BM2214960def-001 | BM2214960def |  | 1 | 0.000000 | 0.000000 | 0.000000 | 0 | 1 | 2026-05-03 18:25:12.049084 | 2026-05-03 18:25:12.049084 |
| IT22069368-001 | IT22069368 |  | 1 | 0.999702 | 0.000298 | 0.000298 | 0 | 0 | 2026-05-03 10:26:20.642081 | 2026-05-03 10:26:20.642081 |
| IT22106124-001 | IT22106124 |  | 1 | 0.989011 | 0.010989 | 0.010989 | 0 | 0 | 2026-05-03 12:20:20.965459 | 2026-05-03 12:20:20.965459 |
| IT22106124-002 | IT22106124 |  | 1 | 0.088101 | 0.911899 | 0.911899 | 1 | 1 | 2026-05-03 12:23:33.002131 | 2026-05-03 12:23:33.002131 |
| IT22138040-001 | IT22138040 |  | 1 | -0.254475 | 1.254475 | 1.254475 | 1 | 1 | 2026-05-03 17:42:09.563218 | 2026-05-03 17:42:09.563218 |
| IT22266828-002 | IT22266828 |  | 1 | 0.999286 | 0.000714 | 0.000714 | 0 | 0 | 2026-05-03 11:01:17.235091 | 2026-05-03 11:01:17.235091 |
| IT22267122-001 | IT22267122 |  | 1 | 0.975373 | 0.024627 | 0.024627 | 0 | 0 | 2026-05-04 10:10:18.671509 | 2026-05-04 10:10:18.671509 |
| IT22277190-001 | IT22277190 |  | 1 | 0.990684 | 0.009316 | 0.009316 | 0 | 0 | 2026-05-03 18:40:30.202193 | 2026-05-03 18:40:30.202193 |
| it22081520-001 | it22081520 |  | 1 | 0.999299 | 0.000701 | 0.000701 | 0 | 0 | 2026-05-03 10:23:59.703776 | 2026-05-03 10:23:59.703776 |
| it22081520-002 | it22081520 |  | 1 | 0.999436 | 0.000564 | 0.000564 | 0 | 0 | 2026-05-03 10:29:30.705938 | 2026-05-03 10:29:30.705938 |

### Auth Timeline Events

| id | user | session | offset_s | similarity | risk | auth | confidence | anomaly | struggling | sample | threshold | phase |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 8 | BM2214960 | BM2214960-001 | 0 | 0.952880 | 0.047120 | yes | HIGH | no | no |  |  |  |
| 10 | BM2214960 | BM2214960-002 | 0 | 0.908595 | 0.091405 | yes | HIGH | no | no |  |  |  |
| 9 | BM2214960def | BM2214960def-001 | 0 | 0.000000 | 0.000000 | no | LOW | no | no |  |  |  |
| 2 | IT22069368 | IT22069368-001 | 0 | 0.999702 | 0.000298 | yes | HIGH | no | no |  |  |  |
| 5 | IT22106124 | IT22106124-001 | 0 | 0.989011 | 0.010989 | yes | HIGH | no | no |  |  |  |
| 6 | IT22106124 | IT22106124-002 | 0 | 0.088101 | 0.911899 | no | LOW | yes | no |  |  |  |
| 7 | IT22138040 | IT22138040-001 | 0 | -0.254475 | 1.254475 | no | LOW | yes | no |  |  |  |
| 4 | IT22266828 | IT22266828-002 | 0 | 0.999286 | 0.000714 | yes | HIGH | no | no |  |  |  |
| 12 | IT22267122 | IT22267122-001 | 0 | 0.975373 | 0.024627 | yes | HIGH | no | no |  |  |  |
| 11 | IT22277190 | IT22277190-001 | 0 | 0.990684 | 0.009316 | yes | HIGH | no | no |  |  |  |
| 1 | it22081520 | it22081520-001 | 0 | 0.999299 | 0.000701 | yes | HIGH | no | no |  |  |  |
| 3 | it22081520 | it22081520-002 | 0 | 0.999436 | 0.000564 | yes | HIGH | no | no |  |  |  |

## Saved Metric Snapshots

### Metrics Snapshot 1 (2026-05-05 16:32:02.593932)

- Scope: `research`
- Scope ID: `None`
```json
{
  "tests": 28,
  "avgRisk": 0.1996274941733905,
  "records": 60,
  "assumption": "Genuine tests measure false negatives; impostor tests measure false positives.",
  "enrollments": 15,
  "avgSimilarity": 0.8003725058266095,
  "impostorTests": 5,
  "latestSession": "IT22132550-003",
  "falseNegatives": 3,
  "falsePositives": 1,
  "falseNegativeRate": 0.13043478260869565,
  "falsePositiveRate": 0.2,
  "genuineAcceptRate": 0.8695652173913043
}
```
### Metrics Snapshot 2 (2026-05-05 16:32:06.913658)

- Scope: `research`
- Scope ID: `None`
```json
{
  "tests": 28,
  "avgRisk": 0.1996274941733905,
  "records": 60,
  "assumption": "Genuine tests measure false negatives; impostor tests measure false positives.",
  "enrollments": 15,
  "avgSimilarity": 0.8003725058266095,
  "impostorTests": 5,
  "latestSession": "IT22132550-003",
  "falseNegatives": 3,
  "falsePositives": 1,
  "falseNegativeRate": 0.13043478260869565,
  "falsePositiveRate": 0.2,
  "genuineAcceptRate": 0.8695652173913043
}
```

## Behavioral Analysis Cached Outputs

No archives currently contain cached `behavioral_analysis` objects. Several archive rows contain JSON `null`; those are treated as unavailable analysis in this report.

## Complete Per-Test API Response JSON

### Test Record 1: `IT22266828-001` / `IT22266828`

```json
{
  "record": {
    "id": 1,
    "user_id": "IT22266828",
    "session_id": "IT22266828-001",
    "assignment_id": null,
    "course_id": null,
    "created_at": "2026-05-03 14:43:27.463375",
    "student_name": "Hasintha Dilshan",
    "session_index": 1
  },
  "request_json_compact": {
    "userId": "IT22266828",
    "finalCode": "[see final code section: 200 chars]",
    "sessionId": "IT22266828-001",
    "threshold": 0.7,
    "studentName": "Hasintha Dilshan",
    "assignmentId": null,
    "keystrokeEvents": "[omitted: 170 events]"
  },
  "capture_response": {
    "success": true,
    "captured": 170,
    "total_buffered": 170
  },
  "verify_response": {
    "message": "Authenticated",
    "success": true,
    "user_id": "IT22266828",
    "threshold": 0.7,
    "risk_score": 6.961822509765625e-05,
    "similarity": 0.9999303817749023,
    "authenticated": true
  },
  "monitor_response": {
    "status": "COLLECTING_DATA",
    "message": "Collecting baseline data. 0/150 events captured.",
    "success": true,
    "risk_score": 0.0
  },
  "identify_response": {
    "matches": [
      {
        "rank": 1,
        "userId": "IT22266828",
        "confidence": 74.74532723426819,
        "similarity": 0.7474532723426819
      },
      {
        "rank": 2,
        "userId": "it22081520",
        "confidence": 35.39769649505615,
        "similarity": 0.3539769649505615
      },
      {
        "rank": 3,
        "userId": "IT22069368",
        "confidence": 1.529865711927414,
        "similarity": 0.01529865711927414
      }
    ],
    "message": "Identified with MEDIUM confidence",
    "success": true,
    "best_match": {
      "rank": 1,
      "userId": "IT22266828",
      "confidence": 74.74532723426819,
      "similarity": 0.7474532723426819
    },
    "confidence_level": "MEDIUM",
    "total_enrolled_users": 3
  },
  "finalize_response": {
    "message": "Session archived and Redis cleaned up",
    "success": true,
    "assignment_id": null,
    "events_archived": 0
  },
  "analytics_response": {
    "success": true,
    "session_id": "IT22266828-001",
    "risk_timeline": [],
    "friction_points": [],
    "analysis_available": false,
    "behavioral_analysis": null
  }
}
```
### Test Record 2: `it22081520-001` / `it22081520`

```json
{
  "record": {
    "id": 2,
    "user_id": "it22081520",
    "session_id": "it22081520-001",
    "assignment_id": null,
    "course_id": null,
    "created_at": "2026-05-03 15:53:59.819025",
    "student_name": "Dananjaya Ariyasena",
    "session_index": 1
  },
  "request_json_compact": {
    "userId": "it22081520",
    "finalCode": "[see final code section: 270 chars]",
    "sessionId": "it22081520-001",
    "threshold": 0.7,
    "studentName": "Dananjaya Ariyasena",
    "assignmentId": null,
    "keystrokeEvents": "[omitted: 193 events]"
  },
  "capture_response": {
    "success": true,
    "captured": 193,
    "total_buffered": 193
  },
  "verify_response": {
    "message": "Authenticated",
    "success": true,
    "user_id": "it22081520",
    "threshold": 0.7,
    "risk_score": 0.0008810758590698242,
    "similarity": 0.9991189241409302,
    "authenticated": true
  },
  "monitor_response": {
    "status": "AUTHENTICATED",
    "message": "Continuous authentication: AUTHENTICATED",
    "success": true,
    "threshold": 0.7,
    "authenticated": true,
    "max_risk_score": 0.0010485649108886719,
    "min_similarity": 0.9989514350891113,
    "individual_scores": [
      0.0010485649108886719,
      0.0003542900085449219
    ],
    "average_risk_score": 0.0007014274597167969,
    "average_similarity": 0.9992985725402832,
    "verification_count": 2
  },
  "identify_response": {
    "matches": [
      {
        "rank": 1,
        "userId": "it22081520",
        "confidence": 98.89650344848633,
        "similarity": 0.9889650344848633
      },
      {
        "rank": 2,
        "userId": "IT22069368",
        "confidence": 79.16657328605652,
        "similarity": 0.7916657328605652
      },
      {
        "rank": 3,
        "userId": "IT22266828",
        "confidence": 40.395525097846985,
        "similarity": 0.40395525097846985
      }
    ],
    "message": "Identified with HIGH confidence",
    "success": true,
    "best_match": {
      "rank": 1,
      "userId": "it22081520",
      "confidence": 98.89650344848633,
      "similarity": 0.9889650344848633
    },
    "confidence_level": "HIGH",
    "total_enrolled_users": 3
  },
  "finalize_response": {
    "message": "Session archived and Redis cleaned up",
    "success": true,
    "assignment_id": null,
    "events_archived": 193
  },
  "analytics_response": {
    "success": true,
    "session_id": "it22081520-001",
    "risk_timeline": [
      {
        "is_anomaly": false,
        "risk_score": 0.0007014274597167969,
        "is_struggling": false,
        "offset_seconds": 0,
        "similarity_score": 0.9992985725402832
      }
    ],
    "friction_points": [],
    "analysis_available": false,
    "behavioral_analysis": null
  }
}
```
### Test Record 3: `IT22069368-001` / `IT22069368`

```json
{
  "record": {
    "id": 3,
    "user_id": "IT22069368",
    "session_id": "IT22069368-001",
    "assignment_id": null,
    "course_id": null,
    "created_at": "2026-05-03 15:56:20.703029",
    "student_name": "Sandul Karunarathna",
    "session_index": 1
  },
  "request_json_compact": {
    "userId": "IT22069368",
    "finalCode": "[see final code section: 270 chars]",
    "sessionId": "IT22069368-001",
    "threshold": 0.7,
    "studentName": "Sandul Karunarathna",
    "assignmentId": null,
    "keystrokeEvents": "[omitted: 189 events]"
  },
  "capture_response": {
    "success": true,
    "captured": 189,
    "total_buffered": 189
  },
  "verify_response": {
    "message": "Authenticated",
    "success": true,
    "user_id": "IT22069368",
    "threshold": 0.7,
    "risk_score": 0.0005491375923156738,
    "similarity": 0.9994508624076843,
    "authenticated": true
  },
  "monitor_response": {
    "status": "AUTHENTICATED",
    "message": "Continuous authentication: AUTHENTICATED",
    "success": true,
    "threshold": 0.7,
    "authenticated": true,
    "max_risk_score": 0.0004794597625732422,
    "min_similarity": 0.9995205402374268,
    "individual_scores": [
      0.00011622905731201172,
      0.0004794597625732422
    ],
    "average_risk_score": 0.00029784440994262695,
    "average_similarity": 0.9997021555900574,
    "verification_count": 2
  },
  "identify_response": {
    "matches": [
      {
        "rank": 1,
        "userId": "it22081520",
        "confidence": 88.68508338928223,
        "similarity": 0.8868508338928223
      },
      {
        "rank": 2,
        "userId": "IT22069368",
        "confidence": 87.7886712551117,
        "similarity": 0.8778867125511169
      },
      {
        "rank": 3,
        "userId": "IT22266828",
        "confidence": 45.6171840429306,
        "similarity": 0.45617184042930603
      }
    ],
    "message": "Identified with HIGH confidence",
    "success": true,
    "best_match": {
      "rank": 1,
      "userId": "it22081520",
      "confidence": 88.68508338928223,
      "similarity": 0.8868508338928223
    },
    "confidence_level": "HIGH",
    "total_enrolled_users": 3
  },
  "finalize_response": {
    "message": "Session archived and Redis cleaned up",
    "success": true,
    "assignment_id": null,
    "events_archived": 189
  },
  "analytics_response": {
    "success": true,
    "session_id": "IT22069368-001",
    "risk_timeline": [
      {
        "is_anomaly": false,
        "risk_score": 0.00029784440994262695,
        "is_struggling": false,
        "offset_seconds": 0,
        "similarity_score": 0.9997021555900574
      }
    ],
    "friction_points": [],
    "analysis_available": false,
    "behavioral_analysis": null
  }
}
```
### Test Record 4: `it22081520-002` / `it22081520`

```json
{
  "record": {
    "id": 4,
    "user_id": "it22081520",
    "session_id": "it22081520-002",
    "assignment_id": null,
    "course_id": null,
    "created_at": "2026-05-03 15:59:30.765799",
    "student_name": "Dananjaya Ariyasena",
    "session_index": 2
  },
  "request_json_compact": {
    "userId": "it22081520",
    "finalCode": "[see final code section: 186 chars]",
    "sessionId": "it22081520-002",
    "threshold": 0.7,
    "studentName": "Dananjaya Ariyasena",
    "assignmentId": null,
    "keystrokeEvents": "[omitted: 205 events]"
  },
  "capture_response": {
    "success": true,
    "captured": 205,
    "total_buffered": 205
  },
  "verify_response": {
    "message": "Authenticated",
    "success": true,
    "user_id": "it22081520",
    "threshold": 0.7,
    "risk_score": 0.001999497413635254,
    "similarity": 0.9980005025863647,
    "authenticated": true
  },
  "monitor_response": {
    "status": "AUTHENTICATED",
    "message": "Continuous authentication: AUTHENTICATED",
    "success": true,
    "threshold": 0.7,
    "authenticated": true,
    "max_risk_score": 0.0008800625801086426,
    "min_similarity": 0.9991199374198914,
    "individual_scores": [
      0.0008800625801086426,
      0.00024837255477905273
    ],
    "average_risk_score": 0.0005642175674438477,
    "average_similarity": 0.9994357824325562,
    "verification_count": 2
  },
  "identify_response": {
    "matches": [
      {
        "rank": 1,
        "userId": "IT22266828",
        "confidence": 58.5728645324707,
        "similarity": 0.585728645324707
      },
      {
        "rank": 2,
        "userId": "it22081520",
        "confidence": 29.619115591049194,
        "similarity": 0.29619115591049194
      },
      {
        "rank": 3,
        "userId": "IT22069368",
        "confidence": 27.32526957988739,
        "similarity": 0.2732526957988739
      }
    ],
    "message": "Identified with LOW confidence",
    "success": true,
    "best_match": {
      "rank": 1,
      "userId": "IT22266828",
      "confidence": 58.5728645324707,
      "similarity": 0.585728645324707
    },
    "confidence_level": "LOW",
    "total_enrolled_users": 3
  },
  "finalize_response": {
    "message": "Session archived and Redis cleaned up",
    "success": true,
    "assignment_id": null,
    "events_archived": 205
  },
  "analytics_response": {
    "success": true,
    "session_id": "it22081520-002",
    "risk_timeline": [
      {
        "is_anomaly": false,
        "risk_score": 0.0005642175674438477,
        "is_struggling": false,
        "offset_seconds": 0,
        "similarity_score": 0.9994357824325562
      }
    ],
    "friction_points": [],
    "analysis_available": false,
    "behavioral_analysis": null
  }
}
```
### Test Record 5: `IT22266828-002` / `IT22266828`

```json
{
  "record": {
    "id": 5,
    "user_id": "IT22266828",
    "session_id": "IT22266828-002",
    "assignment_id": null,
    "course_id": null,
    "created_at": "2026-05-03 16:31:17.330644",
    "student_name": "Hasintha Dilshan",
    "session_index": 2
  },
  "request_json_compact": {
    "userId": "IT22266828",
    "finalCode": "[see final code section: 168 chars]",
    "sessionId": "IT22266828-002",
    "threshold": 0.7,
    "studentName": "Hasintha Dilshan",
    "assignmentId": null,
    "keystrokeEvents": "[omitted: 175 events]"
  },
  "capture_response": {
    "success": true,
    "captured": 175,
    "total_buffered": 175
  },
  "verify_response": {
    "message": "Authenticated",
    "success": true,
    "user_id": "IT22266828",
    "threshold": 0.7,
    "risk_score": 0.001094043254852295,
    "similarity": 0.9989059567451477,
    "authenticated": true
  },
  "monitor_response": {
    "status": "AUTHENTICATED",
    "message": "Continuous authentication: AUTHENTICATED",
    "success": true,
    "threshold": 0.7,
    "authenticated": true,
    "max_risk_score": 0.0009251236915588379,
    "min_similarity": 0.9990748763084412,
    "individual_scores": [
      0.0009251236915588379,
      0.000503242015838623
    ],
    "average_risk_score": 0.0007141828536987305,
    "average_similarity": 0.9992858171463013,
    "verification_count": 2
  },
  "identify_response": {
    "matches": [
      {
        "rank": 1,
        "userId": "IT22266828",
        "confidence": 81.91447854042053,
        "similarity": 0.8191447854042053
      },
      {
        "rank": 2,
        "userId": "it22081520",
        "confidence": 11.24788224697113,
        "similarity": 0.1124788224697113
      },
      {
        "rank": 3,
        "userId": "IT22069368",
        "confidence": -28.29219102859497,
        "similarity": -0.2829219102859497
      }
    ],
    "message": "Identified with HIGH confidence",
    "success": true,
    "best_match": {
      "rank": 1,
      "userId": "IT22266828",
      "confidence": 81.91447854042053,
      "similarity": 0.8191447854042053
    },
    "confidence_level": "HIGH",
    "total_enrolled_users": 3
  },
  "finalize_response": {
    "message": "Session archived and Redis cleaned up",
    "success": true,
    "assignment_id": null,
    "events_archived": 175
  },
  "analytics_response": {
    "success": true,
    "session_id": "IT22266828-002",
    "risk_timeline": [
      {
        "is_anomaly": false,
        "risk_score": 0.0007141828536987305,
        "is_struggling": false,
        "offset_seconds": 0,
        "similarity_score": 0.9992858171463013
      }
    ],
    "friction_points": [],
    "analysis_available": false,
    "behavioral_analysis": null
  }
}
```
### Test Record 6: `IT22266828-003` / `IT22266828`

```json
{
  "record": {
    "id": 6,
    "user_id": "IT22266828",
    "session_id": "IT22266828-003",
    "assignment_id": null,
    "course_id": null,
    "created_at": "2026-05-03 17:01:24.302909",
    "student_name": "Hasintha Dilshan",
    "session_index": 3
  },
  "request_json_compact": {
    "userId": "IT22266828",
    "finalCode": "[see final code section: 121 chars]",
    "sessionId": "IT22266828-003",
    "threshold": 0.7,
    "studentName": "Hasintha Dilshan",
    "assignmentId": null,
    "keystrokeEvents": "[omitted: 107 events]"
  },
  "capture_response": {
    "success": true,
    "captured": 107,
    "total_buffered": 107
  },
  "verify_response": {
    "message": "Authenticated",
    "success": true,
    "user_id": "IT22266828",
    "threshold": 0.7,
    "risk_score": 0.29475629329681396,
    "similarity": 0.705243706703186,
    "authenticated": true
  },
  "monitor_response": {
    "status": "COLLECTING_DATA",
    "message": "Collecting baseline data. 107/150 events captured.",
    "success": true,
    "risk_score": 0.0
  },
  "identify_response": {
    "matches": [
      {
        "rank": 1,
        "userId": "IT22266828",
        "confidence": 70.5243706703186,
        "similarity": 0.705243706703186
      },
      {
        "rank": 2,
        "userId": "it22081520",
        "confidence": 53.654223680496216,
        "similarity": 0.5365422368049622
      },
      {
        "rank": 3,
        "userId": "IT22069368",
        "confidence": 30.60525953769684,
        "similarity": 0.3060525953769684
      }
    ],
    "message": "Identified with MEDIUM confidence",
    "success": true,
    "best_match": {
      "rank": 1,
      "userId": "IT22266828",
      "confidence": 70.5243706703186,
      "similarity": 0.705243706703186
    },
    "confidence_level": "MEDIUM",
    "total_enrolled_users": 3
  },
  "finalize_response": {
    "message": "Session archived and Redis cleaned up",
    "success": true,
    "assignment_id": null,
    "events_archived": 107
  },
  "analytics_response": {
    "success": true,
    "session_id": "IT22266828-003",
    "risk_timeline": [],
    "friction_points": [],
    "analysis_available": false,
    "behavioral_analysis": null
  }
}
```
### Test Record 7: `IT22266828-004` / `IT22266828`

```json
{
  "record": {
    "id": 7,
    "user_id": "IT22266828",
    "session_id": "IT22266828-004",
    "assignment_id": null,
    "course_id": null,
    "created_at": "2026-05-03 17:02:53.919437",
    "student_name": "Hasintha Dilshan",
    "session_index": 4
  },
  "request_json_compact": {
    "userId": "IT22266828",
    "finalCode": "[see final code section: 197 chars]",
    "sessionId": "IT22266828-004",
    "threshold": 0.7,
    "studentName": "Hasintha Dilshan",
    "assignmentId": null,
    "keystrokeEvents": "[omitted: 147 events]"
  },
  "capture_response": {
    "success": true,
    "captured": 147,
    "total_buffered": 147
  },
  "verify_response": {
    "message": "Authenticated",
    "success": true,
    "user_id": "IT22266828",
    "threshold": 0.7,
    "risk_score": 0.2424304485321045,
    "similarity": 0.7575695514678955,
    "authenticated": true
  },
  "monitor_response": {
    "status": "COLLECTING_DATA",
    "message": "Collecting baseline data. 147/150 events captured.",
    "success": true,
    "risk_score": 0.0
  },
  "identify_response": {
    "matches": [
      {
        "rank": 1,
        "userId": "IT22266828",
        "confidence": 75.75695514678955,
        "similarity": 0.7575695514678955
      },
      {
        "rank": 2,
        "userId": "it22081520",
        "confidence": 69.72136497497559,
        "similarity": 0.6972136497497559
      },
      {
        "rank": 3,
        "userId": "IT22069368",
        "confidence": 63.60594034194946,
        "similarity": 0.6360594034194946
      }
    ],
    "message": "Identified with MEDIUM confidence",
    "success": true,
    "best_match": {
      "rank": 1,
      "userId": "IT22266828",
      "confidence": 75.75695514678955,
      "similarity": 0.7575695514678955
    },
    "confidence_level": "MEDIUM",
    "total_enrolled_users": 3
  },
  "finalize_response": {
    "message": "Session archived and Redis cleaned up",
    "success": true,
    "assignment_id": null,
    "events_archived": 147
  },
  "analytics_response": {
    "success": true,
    "session_id": "IT22266828-004",
    "risk_timeline": [],
    "friction_points": [],
    "analysis_available": false,
    "behavioral_analysis": null
  }
}
```
### Test Record 8: `IT22106124-001` / `IT22106124`

```json
{
  "record": {
    "id": 8,
    "user_id": "IT22106124",
    "session_id": "IT22106124-001",
    "assignment_id": null,
    "course_id": null,
    "created_at": "2026-05-03 17:50:20.991651",
    "student_name": "M.D.S.Jayasinghe",
    "session_index": 1
  },
  "request_json_compact": {
    "userId": "IT22106124",
    "testType": "genuine",
    "finalCode": "[see final code section: 270 chars]",
    "sessionId": "IT22106124-001",
    "threshold": 0.7,
    "studentName": "M.D.S.Jayasinghe",
    "actualUserId": "IT22106124",
    "assignmentId": null,
    "keystrokeEvents": "[omitted: 184 events]"
  },
  "capture_response": {
    "success": true,
    "captured": 184,
    "total_buffered": 184
  },
  "verify_response": {
    "message": "Authenticated",
    "success": true,
    "user_id": "IT22106124",
    "threshold": 0.7,
    "risk_score": 0.002581179141998291,
    "similarity": 0.9974188208580017,
    "authenticated": true
  },
  "monitor_response": {
    "status": "AUTHENTICATED",
    "message": "Continuous authentication: AUTHENTICATED",
    "success": true,
    "threshold": 0.7,
    "authenticated": true,
    "max_risk_score": 0.013009965419769287,
    "min_similarity": 0.9869900345802307,
    "individual_scores": [
      0.013009965419769287,
      0.0089682936668396
    ],
    "average_risk_score": 0.010989129543304443,
    "average_similarity": 0.9890108704566956,
    "verification_count": 2
  },
  "identify_response": {
    "matches": [
      {
        "rank": 1,
        "userId": "IT22106124",
        "confidence": 99.74188208580017,
        "similarity": 0.9974188208580017
      },
      {
        "rank": 2,
        "userId": "it22081520",
        "confidence": 86.76723837852478,
        "similarity": 0.8676723837852478
      },
      {
        "rank": 3,
        "userId": "IT22069368",
        "confidence": 81.6548228263855,
        "similarity": 0.816548228263855
      }
    ],
    "message": "Identified with HIGH confidence",
    "success": true,
    "best_match": {
      "rank": 1,
      "userId": "IT22106124",
      "confidence": 99.74188208580017,
      "similarity": 0.9974188208580017
    },
    "confidence_level": "HIGH",
    "total_enrolled_users": 5
  },
  "finalize_response": {
    "message": "Session archived and Redis cleaned up",
    "success": true,
    "assignment_id": null,
    "events_archived": 184
  },
  "analytics_response": {
    "success": true,
    "session_id": "IT22106124-001",
    "risk_timeline": [
      {
        "is_anomaly": false,
        "risk_score": 0.010989129543304443,
        "is_struggling": false,
        "offset_seconds": 0,
        "similarity_score": 0.9890108704566956
      }
    ],
    "friction_points": [],
    "analysis_available": false,
    "behavioral_analysis": null
  }
}
```
### Test Record 9: `IT22106124-002` / `IT22106124`

```json
{
  "record": {
    "id": 9,
    "user_id": "IT22106124",
    "session_id": "IT22106124-002",
    "assignment_id": null,
    "course_id": null,
    "created_at": "2026-05-03 17:53:33.062075",
    "student_name": "M.D.S.Jayasinghe",
    "session_index": 2
  },
  "request_json_compact": {
    "userId": "IT22106124",
    "testType": "impostor",
    "finalCode": "[see final code section: 247 chars]",
    "sessionId": "IT22106124-002",
    "threshold": 0.7,
    "studentName": "M.D.S.Jayasinghe",
    "actualUserId": "IT22266828",
    "assignmentId": null,
    "keystrokeEvents": "[omitted: 198 events]"
  },
  "capture_response": {
    "success": true,
    "captured": 198,
    "total_buffered": 198
  },
  "verify_response": {
    "message": "Authentication failed",
    "success": true,
    "user_id": "IT22106124",
    "threshold": 0.7,
    "risk_score": 0.5413102209568024,
    "similarity": 0.45868977904319763,
    "authenticated": false
  },
  "monitor_response": {
    "status": "REJECTED",
    "message": "Continuous authentication: REJECTED",
    "success": true,
    "threshold": 0.7,
    "authenticated": false,
    "max_risk_score": 1.0560086891055107,
    "min_similarity": -0.05600868910551071,
    "individual_scores": [
      1.0560086891055107,
      0.76778943836689
    ],
    "average_risk_score": 0.9118990637362003,
    "average_similarity": 0.08810093626379967,
    "verification_count": 2
  },
  "identify_response": {
    "matches": [
      {
        "rank": 1,
        "userId": "it22081520",
        "confidence": 81.02504014968872,
        "similarity": 0.8102504014968872
      },
      {
        "rank": 2,
        "userId": "IT22266828",
        "confidence": 77.6712954044342,
        "similarity": 0.776712954044342
      },
      {
        "rank": 3,
        "userId": "IT22069368",
        "confidence": 77.23599076271057,
        "similarity": 0.7723599076271057
      }
    ],
    "message": "Identified with HIGH confidence",
    "success": true,
    "best_match": {
      "rank": 1,
      "userId": "it22081520",
      "confidence": 81.02504014968872,
      "similarity": 0.8102504014968872
    },
    "confidence_level": "HIGH",
    "total_enrolled_users": 5
  },
  "finalize_response": {
    "message": "Session archived and Redis cleaned up",
    "success": true,
    "assignment_id": null,
    "events_archived": 198
  },
  "analytics_response": {
    "success": true,
    "session_id": "IT22106124-002",
    "risk_timeline": [
      {
        "is_anomaly": true,
        "risk_score": 0.9118990637362003,
        "is_struggling": false,
        "offset_seconds": 0,
        "similarity_score": 0.08810093626379967
      }
    ],
    "friction_points": [],
    "analysis_available": false,
    "behavioral_analysis": null
  }
}
```
### Test Record 10: `IT22251596-001` / `IT22251596`

```json
{
  "record": {
    "id": 10,
    "user_id": "IT22251596",
    "session_id": "IT22251596-001",
    "assignment_id": null,
    "course_id": null,
    "created_at": "2026-05-03 18:03:32.371681",
    "student_name": "Ranuga Senadeeera",
    "session_index": 1
  },
  "request_json_compact": {
    "userId": "IT22251596",
    "testType": "genuine",
    "finalCode": "[see final code section: 137 chars]",
    "sessionId": "IT22251596-001",
    "threshold": 0.7,
    "studentName": "Ranuga Senadeeera",
    "actualUserId": "IT22251596",
    "assignmentId": null,
    "keystrokeEvents": "[omitted: 115 events]"
  },
  "capture_response": {
    "success": true,
    "captured": 115,
    "total_buffered": 115
  },
  "verify_response": {
    "message": "Authenticated",
    "success": true,
    "user_id": "IT22251596",
    "threshold": 0.7,
    "risk_score": 0.034261226654052734,
    "similarity": 0.9657387733459473,
    "authenticated": true
  },
  "monitor_response": {
    "status": "COLLECTING_DATA",
    "message": "Collecting baseline data. 115/150 events captured.",
    "success": true,
    "risk_score": 0.0
  },
  "identify_response": {
    "matches": [
      {
        "rank": 1,
        "userId": "IT22251596",
        "confidence": 96.57387733459473,
        "similarity": 0.9657387733459473
      },
      {
        "rank": 2,
        "userId": "IT22069368",
        "confidence": 93.22763085365295,
        "similarity": 0.9322763085365295
      },
      {
        "rank": 3,
        "userId": "it22081520",
        "confidence": 88.56548070907593,
        "similarity": 0.8856548070907593
      }
    ],
    "message": "Identified with HIGH confidence",
    "success": true,
    "best_match": {
      "rank": 1,
      "userId": "IT22251596",
      "confidence": 96.57387733459473,
      "similarity": 0.9657387733459473
    },
    "confidence_level": "HIGH",
    "total_enrolled_users": 6
  },
  "finalize_response": {
    "message": "Session archived and Redis cleaned up",
    "success": true,
    "assignment_id": null,
    "events_archived": 115
  },
  "analytics_response": {
    "success": true,
    "session_id": "IT22251596-001",
    "risk_timeline": [],
    "friction_points": [],
    "analysis_available": false,
    "behavioral_analysis": null
  }
}
```
### Test Record 11: `IT22132550-001` / `IT22132550`

```json
{
  "record": {
    "id": 11,
    "user_id": "IT22132550",
    "session_id": "IT22132550-001",
    "assignment_id": null,
    "course_id": null,
    "created_at": "2026-05-03 18:11:58.178239",
    "student_name": "Nisal Gunawardana",
    "session_index": 1
  },
  "request_json_compact": {
    "userId": "IT22132550",
    "testType": "genuine",
    "finalCode": "[see final code section: 104 chars]",
    "sessionId": "IT22132550-001",
    "threshold": 0.7,
    "studentName": "Nisal Gunawardana",
    "actualUserId": "IT22132550",
    "assignmentId": null,
    "keystrokeEvents": "[omitted: 117 events]"
  },
  "capture_response": {
    "success": true,
    "captured": 117,
    "total_buffered": 117
  },
  "verify_response": {
    "message": "Authenticated",
    "success": true,
    "user_id": "IT22132550",
    "threshold": 0.7,
    "risk_score": 0.05941039323806763,
    "similarity": 0.9405896067619324,
    "authenticated": true
  },
  "monitor_response": {
    "status": "COLLECTING_DATA",
    "message": "Collecting baseline data. 117/150 events captured.",
    "success": true,
    "risk_score": 0.0
  },
  "identify_response": {
    "matches": [
      {
        "rank": 1,
        "userId": "IT22251596",
        "confidence": 95.91355323791504,
        "similarity": 0.9591355323791504
      },
      {
        "rank": 2,
        "userId": "IT22132550",
        "confidence": 94.05896067619324,
        "similarity": 0.9405896067619324
      },
      {
        "rank": 3,
        "userId": "IT22106124",
        "confidence": 92.03152656555176,
        "similarity": 0.9203152656555176
      }
    ],
    "message": "Identified with HIGH confidence",
    "success": true,
    "best_match": {
      "rank": 1,
      "userId": "IT22251596",
      "confidence": 95.91355323791504,
      "similarity": 0.9591355323791504
    },
    "confidence_level": "HIGH",
    "total_enrolled_users": 7
  },
  "finalize_response": {
    "message": "Session archived and Redis cleaned up",
    "success": true,
    "assignment_id": null,
    "events_archived": 117
  },
  "analytics_response": {
    "success": true,
    "session_id": "IT22132550-001",
    "risk_timeline": [],
    "friction_points": [],
    "analysis_available": false,
    "behavioral_analysis": null
  }
}
```
### Test Record 12: `IT22132550-002` / `IT22132550`

```json
{
  "record": {
    "id": 12,
    "user_id": "IT22132550",
    "session_id": "IT22132550-002",
    "assignment_id": null,
    "course_id": null,
    "created_at": "2026-05-03 18:13:33.337001",
    "student_name": "Nisal Gunawardana",
    "session_index": 2
  },
  "request_json_compact": {
    "userId": "IT22132550",
    "testType": "impostor",
    "finalCode": "[see final code section: 161 chars]",
    "sessionId": "IT22132550-002",
    "threshold": 0.7,
    "studentName": "Nisal Gunawardana",
    "actualUserId": "IT22266828",
    "assignmentId": null,
    "keystrokeEvents": "[omitted: 117 events]"
  },
  "capture_response": {
    "success": true,
    "captured": 117,
    "total_buffered": 117
  },
  "verify_response": {
    "message": "Authentication failed",
    "success": true,
    "user_id": "IT22132550",
    "threshold": 0.7,
    "risk_score": 0.32902151346206665,
    "similarity": 0.6709784865379333,
    "authenticated": false
  },
  "monitor_response": {
    "status": "COLLECTING_DATA",
    "message": "Collecting baseline data. 117/150 events captured.",
    "success": true,
    "risk_score": 0.0
  },
  "identify_response": {
    "matches": [
      {
        "rank": 1,
        "userId": "IT22266828",
        "confidence": 80.20091652870178,
        "similarity": 0.8020091652870178
      },
      {
        "rank": 2,
        "userId": "it22081520",
        "confidence": 76.5006959438324,
        "similarity": 0.765006959438324
      },
      {
        "rank": 3,
        "userId": "IT22132550",
        "confidence": 67.09784865379333,
        "similarity": 0.6709784865379333
      }
    ],
    "message": "Identified with HIGH confidence",
    "success": true,
    "best_match": {
      "rank": 1,
      "userId": "IT22266828",
      "confidence": 80.20091652870178,
      "similarity": 0.8020091652870178
    },
    "confidence_level": "HIGH",
    "total_enrolled_users": 7
  },
  "finalize_response": {
    "message": "Session archived and Redis cleaned up",
    "success": true,
    "assignment_id": null,
    "events_archived": 117
  },
  "analytics_response": {
    "success": true,
    "session_id": "IT22132550-002",
    "risk_timeline": [],
    "friction_points": [],
    "analysis_available": false,
    "behavioral_analysis": null
  }
}
```
### Test Record 13: `IT22138422-001` / `IT22138422`

```json
{
  "record": {
    "id": 13,
    "user_id": "IT22138422",
    "session_id": "IT22138422-001",
    "assignment_id": null,
    "course_id": null,
    "created_at": "2026-05-03 18:29:15.275774",
    "student_name": null,
    "session_index": 1
  },
  "request_json_compact": {
    "userId": "IT22138422",
    "testType": "genuine",
    "finalCode": "[see final code section: 131 chars]",
    "sessionId": "IT22138422-001",
    "threshold": 0.7,
    "studentName": null,
    "actualUserId": "IT22138422",
    "assignmentId": null,
    "keystrokeEvents": "[omitted: 119 events]"
  },
  "capture_response": {
    "success": true,
    "captured": 119,
    "total_buffered": 119
  },
  "verify_response": {
    "message": "Authenticated",
    "success": true,
    "user_id": "IT22138422",
    "threshold": 0.7,
    "risk_score": 0.013445019721984863,
    "similarity": 0.9865549802780151,
    "authenticated": true
  },
  "monitor_response": {
    "status": "COLLECTING_DATA",
    "message": "Collecting baseline data. 119/150 events captured.",
    "success": true,
    "risk_score": 0.0
  },
  "identify_response": {
    "matches": [
      {
        "rank": 1,
        "userId": "IT22138422",
        "confidence": 98.65549802780151,
        "similarity": 0.9865549802780151
      },
      {
        "rank": 2,
        "userId": "IT22132550",
        "confidence": 97.23426103591919,
        "similarity": 0.9723426103591919
      },
      {
        "rank": 3,
        "userId": "it22081520",
        "confidence": 93.69520545005798,
        "similarity": 0.9369520545005798
      }
    ],
    "message": "Identified with HIGH confidence",
    "success": true,
    "best_match": {
      "rank": 1,
      "userId": "IT22138422",
      "confidence": 98.65549802780151,
      "similarity": 0.9865549802780151
    },
    "confidence_level": "HIGH",
    "total_enrolled_users": 8
  },
  "finalize_response": {
    "message": "Session archived and Redis cleaned up",
    "success": true,
    "assignment_id": null,
    "events_archived": 119
  },
  "analytics_response": {
    "success": true,
    "session_id": "IT22138422-001",
    "risk_timeline": [],
    "friction_points": [],
    "analysis_available": false,
    "behavioral_analysis": null
  }
}
```
### Test Record 14: `IT22069368-002` / `IT22069368`

```json
{
  "record": {
    "id": 14,
    "user_id": "IT22069368",
    "session_id": "IT22069368-002",
    "assignment_id": null,
    "course_id": null,
    "created_at": "2026-05-03 19:03:47.217590",
    "student_name": "Sandul Karunarathna",
    "session_index": 2
  },
  "request_json_compact": {
    "userId": "IT22069368",
    "testType": "genuine",
    "finalCode": "[see final code section: 137 chars]",
    "sessionId": "IT22069368-002",
    "threshold": 0.7,
    "studentName": "Sandul Karunarathna",
    "actualUserId": "IT22069368",
    "assignmentId": null,
    "keystrokeEvents": "[omitted: 107 events]"
  },
  "capture_response": {
    "success": true,
    "captured": 107,
    "total_buffered": 107
  },
  "verify_response": {
    "message": "Authenticated",
    "success": true,
    "user_id": "IT22069368",
    "threshold": 0.7,
    "risk_score": 0.0169832706451416,
    "similarity": 0.9830167293548584,
    "authenticated": true
  },
  "monitor_response": {
    "status": "COLLECTING_DATA",
    "message": "Collecting baseline data. 107/150 events captured.",
    "success": true,
    "risk_score": 0.0
  },
  "identify_response": {
    "matches": [
      {
        "rank": 1,
        "userId": "IT22069368",
        "confidence": 98.30167293548584,
        "similarity": 0.9830167293548584
      },
      {
        "rank": 2,
        "userId": "IT22251596",
        "confidence": 81.86473846435547,
        "similarity": 0.8186473846435547
      },
      {
        "rank": 3,
        "userId": "it22081520",
        "confidence": 80.00558614730835,
        "similarity": 0.8000558614730835
      }
    ],
    "message": "Identified with HIGH confidence",
    "success": true,
    "best_match": {
      "rank": 1,
      "userId": "IT22069368",
      "confidence": 98.30167293548584,
      "similarity": 0.9830167293548584
    },
    "confidence_level": "HIGH",
    "total_enrolled_users": 8
  },
  "finalize_response": {
    "message": "Session archived and Redis cleaned up",
    "success": true,
    "assignment_id": null,
    "events_archived": 107
  },
  "analytics_response": {
    "success": true,
    "session_id": "IT22069368-002",
    "risk_timeline": [],
    "friction_points": [],
    "analysis_available": false,
    "behavioral_analysis": null
  }
}
```
### Test Record 15: `IT22069368-003` / `IT22069368`

```json
{
  "record": {
    "id": 15,
    "user_id": "IT22069368",
    "session_id": "IT22069368-003",
    "assignment_id": null,
    "course_id": null,
    "created_at": "2026-05-03 19:05:51.069371",
    "student_name": "Sandul Karunarathna",
    "session_index": 3
  },
  "request_json_compact": {
    "userId": "IT22069368",
    "testType": "genuine",
    "finalCode": "[see final code section: 158 chars]",
    "sessionId": "IT22069368-003",
    "threshold": 0.7,
    "studentName": "Sandul Karunarathna",
    "actualUserId": "IT22069368",
    "assignmentId": null,
    "keystrokeEvents": "[omitted: 117 events]"
  },
  "capture_response": {
    "success": true,
    "captured": 117,
    "total_buffered": 117
  },
  "verify_response": {
    "message": "Authentication failed",
    "success": true,
    "user_id": "IT22069368",
    "threshold": 0.7,
    "risk_score": 0.48045122623443604,
    "similarity": 0.519548773765564,
    "authenticated": false
  },
  "monitor_response": {
    "status": "COLLECTING_DATA",
    "message": "Collecting baseline data. 117/150 events captured.",
    "success": true,
    "risk_score": 0.0
  },
  "identify_response": {
    "matches": [
      {
        "rank": 1,
        "userId": "it22081520",
        "confidence": 88.37661743164062,
        "similarity": 0.8837661743164062
      },
      {
        "rank": 2,
        "userId": "IT22138422",
        "confidence": 88.08861970901489,
        "similarity": 0.8808861970901489
      },
      {
        "rank": 3,
        "userId": "IT22132550",
        "confidence": 79.77858185768127,
        "similarity": 0.7977858185768127
      }
    ],
    "message": "Identified with HIGH confidence",
    "success": true,
    "best_match": {
      "rank": 1,
      "userId": "it22081520",
      "confidence": 88.37661743164062,
      "similarity": 0.8837661743164062
    },
    "confidence_level": "HIGH",
    "total_enrolled_users": 8
  },
  "finalize_response": {
    "message": "Session archived and Redis cleaned up",
    "success": true,
    "assignment_id": null,
    "events_archived": 117
  },
  "analytics_response": {
    "success": true,
    "session_id": "IT22069368-003",
    "risk_timeline": [],
    "friction_points": [],
    "analysis_available": false,
    "behavioral_analysis": null
  }
}
```
### Test Record 16: `IT22138040-001` / `IT22138040`

```json
{
  "record": {
    "id": 16,
    "user_id": "IT22138040",
    "session_id": "IT22138040-001",
    "assignment_id": null,
    "course_id": null,
    "created_at": "2026-05-03 23:12:09.624030",
    "student_name": "A.M.T Imalka",
    "session_index": 1
  },
  "request_json_compact": {
    "userId": "IT22138040",
    "testType": "genuine",
    "finalCode": "[see final code section: 281 chars]",
    "sessionId": "IT22138040-001",
    "threshold": 0.7,
    "studentName": "A.M.T Imalka",
    "actualUserId": "IT22138040",
    "assignmentId": null,
    "keystrokeEvents": "[omitted: 164 events]"
  },
  "capture_response": {
    "success": true,
    "captured": 164,
    "total_buffered": 164
  },
  "verify_response": {
    "message": "Authentication failed",
    "success": true,
    "user_id": "IT22138040",
    "threshold": 0.7,
    "risk_score": 1.079549752175808,
    "similarity": -0.07954975217580795,
    "authenticated": false
  },
  "monitor_response": {
    "status": "REJECTED",
    "message": "Continuous authentication: REJECTED",
    "success": true,
    "threshold": 0.7,
    "authenticated": false,
    "max_risk_score": 1.3158394694328308,
    "min_similarity": -0.3158394694328308,
    "individual_scores": [
      1.3158394694328308,
      1.1931097209453583
    ],
    "average_risk_score": 1.2544745951890945,
    "average_similarity": -0.25447459518909454,
    "verification_count": 2
  },
  "identify_response": {
    "matches": [
      {
        "rank": 1,
        "userId": "IT22106124",
        "confidence": 86.39332056045532,
        "similarity": 0.8639332056045532
      },
      {
        "rank": 2,
        "userId": "IT22138422",
        "confidence": 86.06225252151489,
        "similarity": 0.8606225252151489
      },
      {
        "rank": 3,
        "userId": "it22081520",
        "confidence": 84.05200242996216,
        "similarity": 0.8405200242996216
      }
    ],
    "message": "Identified with HIGH confidence",
    "success": true,
    "best_match": {
      "rank": 1,
      "userId": "IT22106124",
      "confidence": 86.39332056045532,
      "similarity": 0.8639332056045532
    },
    "confidence_level": "HIGH",
    "total_enrolled_users": 9
  },
  "finalize_response": {
    "message": "Session archived and Redis cleaned up",
    "success": true,
    "assignment_id": null,
    "events_archived": 164
  },
  "analytics_response": {
    "success": true,
    "session_id": "IT22138040-001",
    "risk_timeline": [
      {
        "is_anomaly": true,
        "risk_score": 1.2544745951890945,
        "is_struggling": false,
        "offset_seconds": 0,
        "similarity_score": -0.25447459518909454
      }
    ],
    "friction_points": [],
    "analysis_available": false,
    "behavioral_analysis": null
  }
}
```
### Test Record 17: `BM2214960-001` / `BM2214960`

```json
{
  "record": {
    "id": 17,
    "user_id": "BM2214960",
    "session_id": "BM2214960-001",
    "assignment_id": null,
    "course_id": null,
    "created_at": "2026-05-03 23:47:18.857306",
    "student_name": "Thushan Imalka",
    "session_index": 1
  },
  "request_json_compact": {
    "userId": "BM2214960",
    "testType": "genuine",
    "finalCode": "[see final code section: 265 chars]",
    "sessionId": "BM2214960-001",
    "threshold": 0.7,
    "studentName": "Thushan Imalka",
    "actualUserId": "BM2214960",
    "assignmentId": null,
    "keystrokeEvents": "[omitted: 186 events]"
  },
  "capture_response": {
    "success": true,
    "captured": 186,
    "total_buffered": 186
  },
  "verify_response": {
    "message": "Authenticated",
    "success": true,
    "user_id": "BM2214960",
    "threshold": 0.7,
    "risk_score": 0.019575834274291992,
    "similarity": 0.980424165725708,
    "authenticated": true
  },
  "monitor_response": {
    "status": "AUTHENTICATED",
    "message": "Continuous authentication: AUTHENTICATED",
    "success": true,
    "threshold": 0.7,
    "authenticated": true,
    "max_risk_score": 0.06593424081802368,
    "min_similarity": 0.9340657591819763,
    "individual_scores": [
      0.06593424081802368,
      0.02830672264099121
    ],
    "average_risk_score": 0.047120481729507446,
    "average_similarity": 0.9528795182704926,
    "verification_count": 2
  },
  "identify_response": {
    "matches": [
      {
        "rank": 1,
        "userId": "BM2214960",
        "confidence": 98.0424165725708,
        "similarity": 0.980424165725708
      },
      {
        "rank": 2,
        "userId": "IT22138422",
        "confidence": 90.98774790763855,
        "similarity": 0.9098774790763855
      },
      {
        "rank": 3,
        "userId": "it22081520",
        "confidence": 87.2680127620697,
        "similarity": 0.872680127620697
      }
    ],
    "message": "Identified with HIGH confidence",
    "success": true,
    "best_match": {
      "rank": 1,
      "userId": "BM2214960",
      "confidence": 98.0424165725708,
      "similarity": 0.980424165725708
    },
    "confidence_level": "HIGH",
    "total_enrolled_users": 10
  },
  "finalize_response": {
    "message": "Session archived and Redis cleaned up",
    "success": true,
    "assignment_id": null,
    "events_archived": 186
  },
  "analytics_response": {
    "success": true,
    "session_id": "BM2214960-001",
    "risk_timeline": [
      {
        "is_anomaly": false,
        "risk_score": 0.047120481729507446,
        "is_struggling": false,
        "offset_seconds": 0,
        "similarity_score": 0.9528795182704926
      }
    ],
    "friction_points": [],
    "analysis_available": false,
    "behavioral_analysis": null
  }
}
```
### Test Record 18: `BM2214960def-001` / `BM2214960def`

```json
{
  "record": {
    "id": 18,
    "user_id": "BM2214960def",
    "session_id": "BM2214960def-001",
    "assignment_id": null,
    "course_id": null,
    "created_at": "2026-05-03 23:55:12.147776",
    "student_name": null,
    "session_index": 1
  },
  "request_json_compact": {
    "userId": "BM2214960def",
    "testType": "genuine",
    "finalCode": "[see final code section: 203 chars]",
    "sessionId": "BM2214960def-001",
    "threshold": 0.7,
    "studentName": null,
    "actualUserId": "BM2214960def",
    "assignmentId": null,
    "keystrokeEvents": "[omitted: 421 events]"
  },
  "capture_response": {
    "success": true,
    "captured": 421,
    "total_buffered": 421
  },
  "verify_response": {
    "message": "User not enrolled",
    "success": false,
    "risk_score": 1.0,
    "authenticated": false
  },
  "monitor_response": {
    "status": "ERROR",
    "message": "User not enrolled",
    "success": false
  },
  "identify_response": {
    "matches": [
      {
        "rank": 1,
        "userId": "BM2214960",
        "confidence": 89.44786787033081,
        "similarity": 0.8944786787033081
      },
      {
        "rank": 2,
        "userId": "it22081520",
        "confidence": 88.66817355155945,
        "similarity": 0.8866817355155945
      },
      {
        "rank": 3,
        "userId": "IT22138422",
        "confidence": 88.58992457389832,
        "similarity": 0.8858992457389832
      }
    ],
    "message": "Identified with HIGH confidence",
    "success": true,
    "best_match": {
      "rank": 1,
      "userId": "BM2214960",
      "confidence": 89.44786787033081,
      "similarity": 0.8944786787033081
    },
    "confidence_level": "HIGH",
    "total_enrolled_users": 10
  },
  "finalize_response": {
    "message": "Session archived and Redis cleaned up",
    "success": true,
    "assignment_id": null,
    "events_archived": 421
  },
  "analytics_response": {
    "success": true,
    "session_id": "BM2214960def-001",
    "risk_timeline": [
      {
        "is_anomaly": false,
        "risk_score": 0.0,
        "is_struggling": false,
        "offset_seconds": 0,
        "similarity_score": 0.0
      }
    ],
    "friction_points": [],
    "analysis_available": false,
    "behavioral_analysis": null
  }
}
```
### Test Record 19: `BM2214960-002` / `BM2214960`

```json
{
  "record": {
    "id": 19,
    "user_id": "BM2214960",
    "session_id": "BM2214960-002",
    "assignment_id": null,
    "course_id": null,
    "created_at": "2026-05-03 23:56:45.030261",
    "student_name": "Thushan Imalka",
    "session_index": 2
  },
  "request_json_compact": {
    "userId": "BM2214960",
    "testType": "genuine",
    "finalCode": "[see final code section: 203 chars]",
    "sessionId": "BM2214960-002",
    "threshold": 0.7,
    "studentName": "Thushan Imalka",
    "actualUserId": "BM2214960",
    "assignmentId": null,
    "keystrokeEvents": "[omitted: 421 events]"
  },
  "capture_response": {
    "success": true,
    "captured": 421,
    "total_buffered": 421
  },
  "verify_response": {
    "message": "Authenticated",
    "success": true,
    "user_id": "BM2214960",
    "threshold": 0.7,
    "risk_score": 0.1055213212966919,
    "similarity": 0.8944786787033081,
    "authenticated": true
  },
  "monitor_response": {
    "status": "AUTHENTICATED",
    "message": "Continuous authentication: AUTHENTICATED",
    "success": true,
    "threshold": 0.7,
    "authenticated": true,
    "max_risk_score": 0.19092392921447754,
    "min_similarity": 0.8090760707855225,
    "individual_scores": [
      0.04414057731628418,
      0.0690111517906189,
      0.19092392921447754,
      0.0615459680557251
    ],
    "average_risk_score": 0.09140540659427643,
    "average_similarity": 0.9085945934057236,
    "verification_count": 4
  },
  "identify_response": {
    "matches": [
      {
        "rank": 1,
        "userId": "BM2214960",
        "confidence": 89.44786787033081,
        "similarity": 0.8944786787033081
      },
      {
        "rank": 2,
        "userId": "it22081520",
        "confidence": 88.66817355155945,
        "similarity": 0.8866817355155945
      },
      {
        "rank": 3,
        "userId": "IT22138422",
        "confidence": 88.58992457389832,
        "similarity": 0.8858992457389832
      }
    ],
    "message": "Identified with HIGH confidence",
    "success": true,
    "best_match": {
      "rank": 1,
      "userId": "BM2214960",
      "confidence": 89.44786787033081,
      "similarity": 0.8944786787033081
    },
    "confidence_level": "HIGH",
    "total_enrolled_users": 10
  },
  "finalize_response": {
    "message": "Session archived and Redis cleaned up",
    "success": true,
    "assignment_id": null,
    "events_archived": 421
  },
  "analytics_response": {
    "success": true,
    "session_id": "BM2214960-002",
    "risk_timeline": [
      {
        "is_anomaly": false,
        "risk_score": 0.09140540659427643,
        "is_struggling": false,
        "offset_seconds": 0,
        "similarity_score": 0.9085945934057236
      }
    ],
    "friction_points": [],
    "analysis_available": false,
    "behavioral_analysis": null
  }
}
```
### Test Record 20: `IT22277190-001` / `IT22277190`

```json
{
  "record": {
    "id": 20,
    "user_id": "IT22277190",
    "session_id": "IT22277190-001",
    "assignment_id": null,
    "course_id": null,
    "created_at": "2026-05-04 00:10:30.291695",
    "student_name": "Rathnayaka H M  S S",
    "session_index": 1
  },
  "request_json_compact": {
    "userId": "IT22277190",
    "testType": "genuine",
    "finalCode": "[see final code section: 219 chars]",
    "sessionId": "IT22277190-001",
    "threshold": 0.7,
    "studentName": "Rathnayaka H M  S S",
    "actualUserId": "IT22277190",
    "assignmentId": null,
    "keystrokeEvents": "[omitted: 155 events]"
  },
  "capture_response": {
    "success": true,
    "captured": 155,
    "total_buffered": 155
  },
  "verify_response": {
    "message": "Authenticated",
    "success": true,
    "user_id": "IT22277190",
    "threshold": 0.7,
    "risk_score": 0.012851119041442871,
    "similarity": 0.9871488809585571,
    "authenticated": true
  },
  "monitor_response": {
    "status": "AUTHENTICATED",
    "message": "Continuous authentication: AUTHENTICATED",
    "success": true,
    "threshold": 0.7,
    "authenticated": true,
    "max_risk_score": 0.009740948677062988,
    "min_similarity": 0.990259051322937,
    "individual_scores": [
      0.008890748023986816,
      0.009740948677062988
    ],
    "average_risk_score": 0.009315848350524902,
    "average_similarity": 0.9906841516494751,
    "verification_count": 2
  },
  "identify_response": {
    "matches": [
      {
        "rank": 1,
        "userId": "it22081520",
        "confidence": 99.0609347820282,
        "similarity": 0.990609347820282
      },
      {
        "rank": 2,
        "userId": "IT22277190",
        "confidence": 98.71488809585571,
        "similarity": 0.9871488809585571
      },
      {
        "rank": 3,
        "userId": "IT22251596",
        "confidence": 90.1591956615448,
        "similarity": 0.901591956615448
      }
    ],
    "message": "Identified with HIGH confidence",
    "success": true,
    "best_match": {
      "rank": 1,
      "userId": "it22081520",
      "confidence": 99.0609347820282,
      "similarity": 0.990609347820282
    },
    "confidence_level": "HIGH",
    "total_enrolled_users": 11
  },
  "finalize_response": {
    "message": "Session archived and Redis cleaned up",
    "success": true,
    "assignment_id": null,
    "events_archived": 155
  },
  "analytics_response": {
    "success": true,
    "session_id": "IT22277190-001",
    "risk_timeline": [
      {
        "is_anomaly": false,
        "risk_score": 0.009315848350524902,
        "is_struggling": false,
        "offset_seconds": 0,
        "similarity_score": 0.9906841516494751
      }
    ],
    "friction_points": [],
    "analysis_available": false,
    "behavioral_analysis": null
  }
}
```
### Test Record 21: `IT22266828-005` / `IT22266828`

```json
{
  "record": {
    "id": 21,
    "user_id": "IT22266828",
    "session_id": "IT22266828-005",
    "assignment_id": null,
    "course_id": null,
    "created_at": "2026-05-04 15:26:49.979701",
    "student_name": "Hasintha Dilshan",
    "session_index": 5
  },
  "request_json_compact": {
    "userId": "IT22266828",
    "testType": "genuine",
    "finalCode": "[see final code section: 147 chars]",
    "sessionId": "IT22266828-005",
    "threshold": 0.7,
    "studentName": "Hasintha Dilshan",
    "actualUserId": "IT22266828",
    "assignmentId": null,
    "keystrokeEvents": "[omitted: 106 events]"
  },
  "capture_response": {
    "success": true,
    "captured": 106,
    "total_buffered": 106
  },
  "verify_response": {
    "message": "Authenticated",
    "success": true,
    "user_id": "IT22266828",
    "threshold": 0.7,
    "risk_score": 0.1602765917778015,
    "similarity": 0.8397234082221985,
    "authenticated": true
  },
  "monitor_response": {
    "status": "COLLECTING_DATA",
    "message": "Collecting baseline data. 106/150 events captured.",
    "success": true,
    "risk_score": 0.0
  },
  "identify_response": {
    "matches": [
      {
        "rank": 1,
        "userId": "IT22266828",
        "confidence": 83.97234082221985,
        "similarity": 0.8397234082221985
      },
      {
        "rank": 2,
        "userId": "it22081520",
        "confidence": 78.78100275993347,
        "similarity": 0.7878100275993347
      },
      {
        "rank": 3,
        "userId": "IT22138422",
        "confidence": 76.66857838630676,
        "similarity": 0.7666857838630676
      }
    ],
    "message": "Identified with HIGH confidence",
    "success": true,
    "best_match": {
      "rank": 1,
      "userId": "IT22266828",
      "confidence": 83.97234082221985,
      "similarity": 0.8397234082221985
    },
    "confidence_level": "HIGH",
    "total_enrolled_users": 11
  },
  "finalize_response": {
    "message": "Session archived and Redis cleaned up",
    "success": true,
    "assignment_id": null,
    "events_archived": 106
  },
  "analytics_response": {
    "success": true,
    "session_id": "IT22266828-005",
    "risk_timeline": [],
    "friction_points": [],
    "analysis_available": false,
    "behavioral_analysis": null
  }
}
```
### Test Record 22: `IT22267122-001` / `IT22267122`

```json
{
  "record": {
    "id": 22,
    "user_id": "IT22267122",
    "session_id": "IT22267122-001",
    "assignment_id": null,
    "course_id": null,
    "created_at": "2026-05-04 15:40:18.771150",
    "student_name": "Parakrama Ekanayake",
    "session_index": 1
  },
  "request_json_compact": {
    "userId": "IT22267122",
    "testType": "genuine",
    "finalCode": "[see final code section: 253 chars]",
    "sessionId": "IT22267122-001",
    "threshold": 0.7,
    "studentName": "Parakrama Ekanayake",
    "actualUserId": "IT22267122",
    "assignmentId": null,
    "keystrokeEvents": "[omitted: 161 events]"
  },
  "capture_response": {
    "success": true,
    "captured": 161,
    "total_buffered": 161
  },
  "verify_response": {
    "message": "Authenticated",
    "success": true,
    "user_id": "IT22267122",
    "threshold": 0.7,
    "risk_score": 0.013274610042572021,
    "similarity": 0.986725389957428,
    "authenticated": true
  },
  "monitor_response": {
    "status": "AUTHENTICATED",
    "message": "Continuous authentication: AUTHENTICATED",
    "success": true,
    "threshold": 0.7,
    "authenticated": true,
    "max_risk_score": 0.02938300371170044,
    "min_similarity": 0.9706169962882996,
    "individual_scores": [
      0.02938300371170044,
      0.019870996475219727
    ],
    "average_risk_score": 0.024627000093460083,
    "average_similarity": 0.9753729999065399,
    "verification_count": 2
  },
  "identify_response": {
    "matches": [
      {
        "rank": 1,
        "userId": "IT22267122",
        "confidence": 98.6725389957428,
        "similarity": 0.986725389957428
      },
      {
        "rank": 2,
        "userId": "IT22106124",
        "confidence": 97.63981699943542,
        "similarity": 0.9763981699943542
      },
      {
        "rank": 3,
        "userId": "IT22138040",
        "confidence": 95.3531265258789,
        "similarity": 0.9535312652587891
      }
    ],
    "message": "Identified with HIGH confidence",
    "success": true,
    "best_match": {
      "rank": 1,
      "userId": "IT22267122",
      "confidence": 98.6725389957428,
      "similarity": 0.986725389957428
    },
    "confidence_level": "HIGH",
    "total_enrolled_users": 12
  },
  "finalize_response": {
    "message": "Session archived and Redis cleaned up",
    "success": true,
    "assignment_id": null,
    "events_archived": 161
  },
  "analytics_response": {
    "success": true,
    "session_id": "IT22267122-001",
    "risk_timeline": [
      {
        "is_anomaly": false,
        "risk_score": 0.024627000093460083,
        "is_struggling": false,
        "offset_seconds": 0,
        "similarity_score": 0.9753729999065399
      }
    ],
    "friction_points": [],
    "analysis_available": false,
    "behavioral_analysis": null
  }
}
```
### Test Record 23: `IT22267122-002` / `IT22267122`

```json
{
  "record": {
    "id": 23,
    "user_id": "IT22267122",
    "session_id": "IT22267122-002",
    "assignment_id": null,
    "course_id": null,
    "created_at": "2026-05-04 15:47:07.092095",
    "student_name": "Parakrama Ekanayake",
    "session_index": 2
  },
  "request_json_compact": {
    "userId": "IT22267122",
    "testType": "impostor",
    "finalCode": "[see final code section: 160 chars]",
    "sessionId": "IT22267122-002",
    "threshold": 0.7,
    "studentName": "Parakrama Ekanayake",
    "assignmentId": null,
    "keystrokeEvents": "[omitted: 119 events]"
  },
  "capture_response": {
    "success": true,
    "captured": 119,
    "total_buffered": 119
  },
  "verify_response": {
    "message": "Authentication failed",
    "success": true,
    "user_id": "IT22267122",
    "threshold": 0.7,
    "risk_score": 0.6445496082305908,
    "similarity": 0.3554503917694092,
    "authenticated": false
  },
  "monitor_response": {
    "status": "COLLECTING_DATA",
    "message": "Collecting baseline data. 119/150 events captured.",
    "success": true,
    "risk_score": 0.0
  },
  "identify_response": {
    "matches": [
      {
        "rank": 1,
        "userId": "IT22266828",
        "confidence": 92.58676767349243,
        "similarity": 0.9258676767349243
      },
      {
        "rank": 2,
        "userId": "it22081520",
        "confidence": 59.18518900871277,
        "similarity": 0.5918518900871277
      },
      {
        "rank": 3,
        "userId": "BM2214960",
        "confidence": 55.91629147529602,
        "similarity": 0.5591629147529602
      }
    ],
    "message": "Identified with HIGH confidence",
    "success": true,
    "best_match": {
      "rank": 1,
      "userId": "IT22266828",
      "confidence": 92.58676767349243,
      "similarity": 0.9258676767349243
    },
    "confidence_level": "HIGH",
    "total_enrolled_users": 12
  },
  "finalize_response": {
    "message": "Session archived and Redis cleaned up",
    "success": true,
    "assignment_id": null,
    "events_archived": 119
  },
  "analytics_response": {
    "success": true,
    "session_id": "IT22267122-002",
    "risk_timeline": [],
    "friction_points": [],
    "analysis_available": false,
    "behavioral_analysis": null
  }
}
```
### Test Record 24: `IT22075758-001` / `IT22075758`

```json
{
  "record": {
    "id": 24,
    "user_id": "IT22075758",
    "session_id": "IT22075758-001",
    "assignment_id": null,
    "course_id": null,
    "created_at": "2026-05-04 16:00:52.168594",
    "student_name": "Chamika Adikari",
    "session_index": 1
  },
  "request_json_compact": {
    "userId": "IT22075758",
    "testType": "genuine",
    "finalCode": "[see final code section: 155 chars]",
    "sessionId": "IT22075758-001",
    "threshold": 0.7,
    "studentName": "Chamika Adikari",
    "assignmentId": null,
    "keystrokeEvents": "[omitted: 117 events]"
  },
  "capture_response": {
    "success": true,
    "captured": 117,
    "total_buffered": 117
  },
  "verify_response": {
    "message": "Authenticated",
    "success": true,
    "user_id": "IT22075758",
    "threshold": 0.7,
    "risk_score": 0.01201707124710083,
    "similarity": 0.9879829287528992,
    "authenticated": true
  },
  "monitor_response": {
    "status": "COLLECTING_DATA",
    "message": "Collecting baseline data. 117/150 events captured.",
    "success": true,
    "risk_score": 0.0
  },
  "identify_response": {
    "matches": [
      {
        "rank": 1,
        "userId": "IT22138040",
        "confidence": 98.8278329372406,
        "similarity": 0.988278329372406
      },
      {
        "rank": 2,
        "userId": "IT22075758",
        "confidence": 98.79829287528992,
        "similarity": 0.9879829287528992
      },
      {
        "rank": 3,
        "userId": "it22081520",
        "confidence": 97.69391417503357,
        "similarity": 0.9769391417503357
      }
    ],
    "message": "Identified with HIGH confidence",
    "success": true,
    "best_match": {
      "rank": 1,
      "userId": "IT22138040",
      "confidence": 98.8278329372406,
      "similarity": 0.988278329372406
    },
    "confidence_level": "HIGH",
    "total_enrolled_users": 13
  },
  "finalize_response": {
    "message": "Session archived and Redis cleaned up",
    "success": true,
    "assignment_id": null,
    "events_archived": 117
  },
  "analytics_response": {
    "success": true,
    "session_id": "IT22075758-001",
    "risk_timeline": [],
    "friction_points": [],
    "analysis_available": false,
    "behavioral_analysis": null
  }
}
```
### Test Record 25: `IT22075758-002` / `IT22075758`

```json
{
  "record": {
    "id": 25,
    "user_id": "IT22075758",
    "session_id": "IT22075758-002",
    "assignment_id": null,
    "course_id": null,
    "created_at": "2026-05-04 16:04:38.177388",
    "student_name": "Chamika Adikari",
    "session_index": 2
  },
  "request_json_compact": {
    "userId": "IT22075758",
    "testType": "impostor",
    "finalCode": "[see final code section: 208 chars]",
    "sessionId": "IT22075758-002",
    "threshold": 0.7,
    "studentName": "Chamika Adikari",
    "assignmentId": null,
    "keystrokeEvents": "[omitted: 141 events]"
  },
  "capture_response": {
    "success": true,
    "captured": 141,
    "total_buffered": 141
  },
  "verify_response": {
    "message": "Authenticated",
    "success": true,
    "user_id": "IT22075758",
    "threshold": 0.7,
    "risk_score": 0.03634357452392578,
    "similarity": 0.9636564254760742,
    "authenticated": true
  },
  "monitor_response": {
    "status": "COLLECTING_DATA",
    "message": "Collecting baseline data. 141/150 events captured.",
    "success": true,
    "risk_score": 0.0
  },
  "identify_response": {
    "matches": [
      {
        "rank": 1,
        "userId": "IT22267122",
        "confidence": 99.22618865966797,
        "similarity": 0.9922618865966797
      },
      {
        "rank": 2,
        "userId": "IT22138422",
        "confidence": 98.05104732513428,
        "similarity": 0.9805104732513428
      },
      {
        "rank": 3,
        "userId": "IT22277190",
        "confidence": 97.25365042686462,
        "similarity": 0.9725365042686462
      }
    ],
    "message": "Identified with HIGH confidence",
    "success": true,
    "best_match": {
      "rank": 1,
      "userId": "IT22267122",
      "confidence": 99.22618865966797,
      "similarity": 0.9922618865966797
    },
    "confidence_level": "HIGH",
    "total_enrolled_users": 13
  },
  "finalize_response": {
    "message": "Session archived and Redis cleaned up",
    "success": true,
    "assignment_id": null,
    "events_archived": 141
  },
  "analytics_response": {
    "success": true,
    "session_id": "IT22075758-002",
    "risk_timeline": [],
    "friction_points": [],
    "analysis_available": false,
    "behavioral_analysis": null
  }
}
```
### Test Record 27: `IT22221032-001` / `IT22221032`

```json
{
  "record": {
    "id": 27,
    "user_id": "IT22221032",
    "session_id": "IT22221032-001",
    "assignment_id": null,
    "course_id": null,
    "created_at": "2026-05-04 16:18:01.699201",
    "student_name": "Yashodara Athapaththu",
    "session_index": 1
  },
  "request_json_compact": {
    "userId": "IT22221032",
    "testType": "genuine",
    "finalCode": "[see final code section: 192 chars]",
    "sessionId": "IT22221032-001",
    "threshold": 0.7,
    "studentName": "Yashodara Athapaththu",
    "assignmentId": null,
    "keystrokeEvents": "[omitted: 139 events]"
  },
  "capture_response": {
    "success": true,
    "captured": 139,
    "total_buffered": 139
  },
  "verify_response": {
    "message": "Authenticated",
    "success": true,
    "user_id": "IT22221032",
    "threshold": 0.7,
    "risk_score": 0.01178961992263794,
    "similarity": 0.9882103800773621,
    "authenticated": true
  },
  "monitor_response": {
    "status": "COLLECTING_DATA",
    "message": "Collecting baseline data. 139/150 events captured.",
    "success": true,
    "risk_score": 0.0
  },
  "identify_response": {
    "matches": [
      {
        "rank": 1,
        "userId": "IT22221032",
        "confidence": 98.8210380077362,
        "similarity": 0.9882103800773621
      },
      {
        "rank": 2,
        "userId": "IT22277190",
        "confidence": 88.30020427703857,
        "similarity": 0.8830020427703857
      },
      {
        "rank": 3,
        "userId": "IT22138422",
        "confidence": 88.20917010307312,
        "similarity": 0.8820917010307312
      }
    ],
    "message": "Identified with HIGH confidence",
    "success": true,
    "best_match": {
      "rank": 1,
      "userId": "IT22221032",
      "confidence": 98.8210380077362,
      "similarity": 0.9882103800773621
    },
    "confidence_level": "HIGH",
    "total_enrolled_users": 14
  },
  "finalize_response": {
    "message": "Session archived and Redis cleaned up",
    "success": true,
    "assignment_id": null,
    "events_archived": 139
  },
  "analytics_response": {
    "success": true,
    "session_id": "IT22221032-001",
    "risk_timeline": [],
    "friction_points": [],
    "analysis_available": false,
    "behavioral_analysis": null
  }
}
```
### Test Record 28: `IT23736382-001` / `IT23736382`

```json
{
  "record": {
    "id": 28,
    "user_id": "IT23736382",
    "session_id": "IT23736382-001",
    "assignment_id": null,
    "course_id": null,
    "created_at": "2026-05-04 16:33:40.063452",
    "student_name": "Thejandeera Sandeepana",
    "session_index": 1
  },
  "request_json_compact": {
    "userId": "IT23736382",
    "testType": "genuine",
    "finalCode": "[see final code section: 134 chars]",
    "sessionId": "IT23736382-001",
    "threshold": 0.7,
    "studentName": "Thejandeera Sandeepana",
    "assignmentId": null,
    "keystrokeEvents": "[omitted: 105 events]"
  },
  "capture_response": {
    "success": true,
    "captured": 105,
    "total_buffered": 105
  },
  "verify_response": {
    "message": "Authenticated",
    "success": true,
    "user_id": "IT23736382",
    "threshold": 0.7,
    "risk_score": 0.085781991481781,
    "similarity": 0.914218008518219,
    "authenticated": true
  },
  "monitor_response": {
    "status": "COLLECTING_DATA",
    "message": "Collecting baseline data. 105/150 events captured.",
    "success": true,
    "risk_score": 0.0
  },
  "identify_response": {
    "matches": [
      {
        "rank": 1,
        "userId": "IT22075758",
        "confidence": 98.95296692848206,
        "similarity": 0.9895296692848206
      },
      {
        "rank": 2,
        "userId": "IT22138040",
        "confidence": 98.63411784172058,
        "similarity": 0.9863411784172058
      },
      {
        "rank": 3,
        "userId": "IT22267122",
        "confidence": 97.22014665603638,
        "similarity": 0.9722014665603638
      }
    ],
    "message": "Identified with HIGH confidence",
    "success": true,
    "best_match": {
      "rank": 1,
      "userId": "IT22075758",
      "confidence": 98.95296692848206,
      "similarity": 0.9895296692848206
    },
    "confidence_level": "HIGH",
    "total_enrolled_users": 15
  },
  "finalize_response": {
    "message": "Session archived and Redis cleaned up",
    "success": true,
    "assignment_id": null,
    "events_archived": 105
  },
  "analytics_response": {
    "success": true,
    "session_id": "IT23736382-001",
    "risk_timeline": [],
    "friction_points": [],
    "analysis_available": false,
    "behavioral_analysis": null
  }
}
```
### Test Record 31: `IT22132550-003` / `IT22132550`

```json
{
  "record": {
    "id": 31,
    "user_id": "IT22132550",
    "session_id": "IT22132550-003",
    "assignment_id": null,
    "course_id": null,
    "created_at": "2026-05-05 16:28:01.838254",
    "student_name": "Nisal Gunawardana",
    "session_index": 3
  },
  "request_json_compact": {
    "userId": "IT22132550",
    "testType": "impostor",
    "finalCode": "[see final code section: 140 chars]",
    "sessionId": "IT22132550-003",
    "threshold": 0.7,
    "studentName": "Nisal Gunawardana",
    "assignmentId": null,
    "keystrokeEvents": "[omitted: 118 events]"
  },
  "capture_response": {
    "success": true,
    "captured": 118,
    "total_buffered": 118
  },
  "verify_response": {
    "message": "Authentication failed",
    "success": true,
    "user_id": "IT22132550",
    "threshold": 0.7,
    "risk_score": 0.4683443307876587,
    "similarity": 0.5316556692123413,
    "authenticated": false
  },
  "monitor_response": {
    "status": "COLLECTING_DATA",
    "message": "Collecting baseline data. 118/150 events captured.",
    "success": true,
    "risk_score": 0.0
  },
  "identify_response": {
    "matches": [
      {
        "rank": 1,
        "userId": "IT22221032",
        "confidence": 97.3909318447113,
        "similarity": 0.973909318447113
      },
      {
        "rank": 2,
        "userId": "IT22266828",
        "confidence": 79.75932359695435,
        "similarity": 0.7975932359695435
      },
      {
        "rank": 3,
        "userId": "BM2214960",
        "confidence": 65.14237523078918,
        "similarity": 0.6514237523078918
      }
    ],
    "message": "Identified with HIGH confidence",
    "success": true,
    "best_match": {
      "rank": 1,
      "userId": "IT22221032",
      "confidence": 97.3909318447113,
      "similarity": 0.973909318447113
    },
    "confidence_level": "HIGH",
    "total_enrolled_users": 15
  },
  "finalize_response": {
    "message": "Session archived and Redis cleaned up",
    "success": true,
    "assignment_id": null,
    "events_archived": 118
  },
  "analytics_response": {
    "success": true,
    "session_id": "IT22132550-003",
    "risk_timeline": [],
    "friction_points": [],
    "analysis_available": false,
    "behavioral_analysis": null
  }
}
```
### Test Record 32: `IT22138040-002` / `IT22138040`

```json
{
  "record": {
    "id": 32,
    "user_id": "IT22138040",
    "session_id": "IT22138040-002",
    "assignment_id": null,
    "course_id": null,
    "created_at": "2026-05-06 07:39:25.981910",
    "student_name": "A.M.T Imalka",
    "session_index": 2
  },
  "request_json_compact": {
    "userId": "IT22138040",
    "testType": "impostor",
    "finalCode": "[see final code section: 142 chars]",
    "sessionId": "IT22138040-002",
    "threshold": 0.7,
    "studentName": "A.M.T Imalka",
    "assignmentId": null,
    "keystrokeEvents": "[omitted: 145 events]"
  },
  "capture_response": {
    "success": true,
    "captured": 145,
    "total_buffered": 145
  },
  "verify_response": {
    "message": "Authentication failed",
    "success": true,
    "user_id": "IT22138040",
    "threshold": 0.7,
    "risk_score": 0.4940149188041687,
    "similarity": 0.5059850811958313,
    "authenticated": false
  },
  "monitor_response": {
    "status": "COLLECTING_DATA",
    "message": "Collecting baseline data. 145/150 events captured.",
    "success": true,
    "risk_score": 0.0
  },
  "identify_response": {
    "matches": [
      {
        "rank": 1,
        "userId": "IT22266828",
        "confidence": 90.25575518608093,
        "similarity": 0.9025575518608093
      },
      {
        "rank": 2,
        "userId": "IT22221032",
        "confidence": 80.04812002182007,
        "similarity": 0.8004812002182007
      },
      {
        "rank": 3,
        "userId": "IT22075758",
        "confidence": 74.22881126403809,
        "similarity": 0.7422881126403809
      }
    ],
    "message": "Identified with HIGH confidence",
    "success": true,
    "best_match": {
      "rank": 1,
      "userId": "IT22266828",
      "confidence": 90.25575518608093,
      "similarity": 0.9025575518608093
    },
    "confidence_level": "HIGH",
    "total_enrolled_users": 15
  },
  "finalize_response": {
    "message": "Session archived and Redis cleaned up",
    "success": true,
    "assignment_id": null,
    "events_archived": 145
  },
  "analytics_response": {
    "success": true,
    "session_id": "IT22138040-002",
    "risk_timeline": [],
    "friction_points": [],
    "analysis_available": false,
    "behavioral_analysis": null
  }
}
```
### Test Record 33: `IT22266828-006` / `IT22266828`

```json
{
  "record": {
    "id": 33,
    "user_id": "IT22266828",
    "session_id": "IT22266828-006",
    "assignment_id": null,
    "course_id": null,
    "created_at": "2026-05-06 07:40:42.179212",
    "student_name": "Hasintha Dilshan",
    "session_index": 6
  },
  "request_json_compact": {
    "userId": "IT22266828",
    "testType": "genuine",
    "finalCode": "[see final code section: 208 chars]",
    "sessionId": "IT22266828-006",
    "threshold": 0.7,
    "studentName": "Hasintha Dilshan",
    "assignmentId": null,
    "keystrokeEvents": "[omitted: 141 events]"
  },
  "capture_response": {
    "success": true,
    "captured": 141,
    "total_buffered": 141
  },
  "verify_response": {
    "message": "Authenticated",
    "success": true,
    "user_id": "IT22266828",
    "threshold": 0.7,
    "risk_score": 0.04541438817977905,
    "similarity": 0.954585611820221,
    "authenticated": true
  },
  "monitor_response": {
    "status": "COLLECTING_DATA",
    "message": "Collecting baseline data. 141/150 events captured.",
    "success": true,
    "risk_score": 0.0
  },
  "identify_response": {
    "matches": [
      {
        "rank": 1,
        "userId": "IT22266828",
        "confidence": 95.4585611820221,
        "similarity": 0.954585611820221
      },
      {
        "rank": 2,
        "userId": "IT22221032",
        "confidence": 81.66384696960449,
        "similarity": 0.8166384696960449
      },
      {
        "rank": 3,
        "userId": "it22081520",
        "confidence": 45.443156361579895,
        "similarity": 0.45443156361579895
      }
    ],
    "message": "Identified with HIGH confidence",
    "success": true,
    "best_match": {
      "rank": 1,
      "userId": "IT22266828",
      "confidence": 95.4585611820221,
      "similarity": 0.954585611820221
    },
    "confidence_level": "HIGH",
    "total_enrolled_users": 15
  },
  "finalize_response": {
    "message": "Session archived and Redis cleaned up",
    "success": true,
    "assignment_id": null,
    "events_archived": 141
  },
  "analytics_response": {
    "success": true,
    "session_id": "IT22266828-006",
    "risk_timeline": [],
    "friction_points": [],
    "analysis_available": false,
    "behavioral_analysis": null
  }
}
```
### Test Record 34: `BM2214960-003` / `BM2214960`

```json
{
  "record": {
    "id": 34,
    "user_id": "BM2214960",
    "session_id": "BM2214960-003",
    "assignment_id": null,
    "course_id": null,
    "created_at": "2026-05-06 07:42:25.286466",
    "student_name": "Thushan Imalka",
    "session_index": 3
  },
  "request_json_compact": {
    "userId": "BM2214960",
    "testType": "impostor",
    "finalCode": "[see final code section: 183 chars]",
    "sessionId": "BM2214960-003",
    "threshold": 0.7,
    "studentName": "Thushan Imalka",
    "assignmentId": null,
    "keystrokeEvents": "[omitted: 135 events]"
  },
  "capture_response": {
    "success": true,
    "captured": 135,
    "total_buffered": 135
  },
  "verify_response": {
    "message": "Authentication failed",
    "success": true,
    "user_id": "BM2214960",
    "threshold": 0.7,
    "risk_score": 0.5714741945266724,
    "similarity": 0.42852580547332764,
    "authenticated": false
  },
  "monitor_response": {
    "status": "COLLECTING_DATA",
    "message": "Collecting baseline data. 135/150 events captured.",
    "success": true,
    "risk_score": 0.0
  },
  "identify_response": {
    "matches": [
      {
        "rank": 1,
        "userId": "IT22266828",
        "confidence": 82.60220885276794,
        "similarity": 0.8260220885276794
      },
      {
        "rank": 2,
        "userId": "IT22221032",
        "confidence": 81.46725296974182,
        "similarity": 0.8146725296974182
      },
      {
        "rank": 3,
        "userId": "IT22075758",
        "confidence": 75.15057325363159,
        "similarity": 0.7515057325363159
      }
    ],
    "message": "Identified with HIGH confidence",
    "success": true,
    "best_match": {
      "rank": 1,
      "userId": "IT22266828",
      "confidence": 82.60220885276794,
      "similarity": 0.8260220885276794
    },
    "confidence_level": "HIGH",
    "total_enrolled_users": 15
  },
  "finalize_response": {
    "message": "Session archived and Redis cleaned up",
    "success": true,
    "assignment_id": null,
    "events_archived": 135
  },
  "analytics_response": {
    "success": true,
    "session_id": "BM2214960-003",
    "risk_timeline": [],
    "friction_points": [],
    "analysis_available": false,
    "behavioral_analysis": null
  }
}
```

## Final Submitted Code Captured During Tests

### Test Record 1: `IT22266828-001` / `IT22266828`

```python
def fizzbuz():
    for number in range(1,101):
        if number % 15 ==0:
            print("Fizzbuzz")
        elif number % 3 == 0:
            print("Buzz")
        else:
            print(number)
```
### Test Record 2: `it22081520-001` / `it22081520`

```python
def fizzbuzz():
    for number in range(1, 101):
        if number % 15 ==0:
            print("FizzBuzz")
        elif number % 3 == 0:
            print("Fizz")
        elif number % 5 == 0:
            print("Buzz")
        else:
            print(number)

fizzbuzz()
```
### Test Record 3: `IT22069368-001` / `IT22069368`

```python
def fizzbuxx():
    for number in range(1,101):
        if number % 15 == 0:
            print("FizzBuzz")
        elif number % 3 == 0:
            print("Fizz")
        elif number % 5 == 0:
            print("Buzz")
        else:
            print(number)

fizzbuzz()
```
### Test Record 4: `it22081520-002` / `it22081520`

```python
#python 3
def main():
    name = "Blaim student"
    course="continuouse authentication"
    print(f"Hello, {name}")
    print(f"Welcome to) {course}")

if _name_ == "_main_":
    main()
```
### Test Record 5: `IT22266828-002` / `IT22266828`

```python
#python 3
def main():
    name = "Continuouse Authentication"
    course = "Continuouse Authentication"
    print(f"Hello,{name}")
    print(f"welcome to {course}")

if
```
### Test Record 6: `IT22266828-003` / `IT22266828`

```python
#Python 3
def main():
    name= "Blaim_Student"
    course = "Continuous Authentication"
    print(f"Hello, {name}")
    
```
### Test Record 7: `IT22266828-004` / `IT22266828`

```python
def fizzbuzz():
    for number in range(1,101):
        if number % 15 ==0:
            print("FizzBuzz")
        elif number%3==0:
            print("FIzz")
        else:
            print(number)
```
### Test Record 8: `IT22106124-001` / `IT22106124`

```python
def fizzbuzz():
    for number in range(1, 101):
        ifnumber % 15 == 0:
            print("fizzbuzz")
        elif number % 3 == 0:
            print("Fizz")
        elif number % 5 == 0:
            print("Buzz")
        else:
            print(number)
fizzbuzz()

```
### Test Record 9: `IT22106124-002` / `IT22106124`

```python
def fizzbuzz():
    for number in range(1,100):
        if number&15 ==0:
            print("Fizzbuss")
        elif number%3==0:
            print("Fizz")
        elif number%5==0:
            print("Buzz")
        else:
            print(number)
```
### Test Record 10: `IT22251596-001` / `IT22251596`

```text
import java.util.ArrayList;

public class NumberUtils {
    public static boolean isPrime(int n){
        if(n < 2) return false;
    }
}
```
### Test Record 11: `IT22132550-001` / `IT22132550`

```python
def fizzbuzz();
for number in range(1,101);
if number % 3 == 0;
print ("Fizzbuzz")
elif number % 3 == 0

```
### Test Record 12: `IT22132550-002` / `IT22132550`

```python
def fizzbuzz():
    for number in range(1,100):
        if number % 15 ==0:
            print("Fizzbuzz")
        elif number % 3 == 0:
            ptint("Fizz")
```
### Test Record 13: `IT22138422-001` / `IT22138422`

```python
def fizzbuzz():
    for number in range(1,100):
        if number %15 ==0:
            print("FizzBuzz")
        else number % 5 ==
```
### Test Record 14: `IT22069368-002` / `IT22069368`

```python
def fizzbuzz():
    for number in range(1, 101):
        if number % 15 == 0:
            print("fizzbuzz")
        elif number % 3 == 0:
```
### Test Record 15: `IT22069368-003` / `IT22069368`

```python
def fizzbus():
    for number in range(1,101):
        if number % 15 ==0:
            print("Fizzbuzz")
        elif number %3 ==0:
            print("Fizz")
```
### Test Record 16: `IT22138040-001` / `IT22138040`

```python
def fizzbuzz():
     for number in range(1,101):
        if number % 15==0
            print("fizzbuzz")
        elif number % 3 ==0
            print("fizzbuzz")
        elif number % 5 ==0
             print("fizzbuzz")
        else 
            print(number)
       

fizzbuzz()
```
### Test Record 17: `BM2214960-001` / `BM2214960`

```python
def fizzbuzz():
    for number in range(1,101):
        if number %15 ==0:
            print("FizzBuzz")
        if number % 3 == 0:
            print("Fizz")
        if number % 5 == 0:
            print("Buzz")
        else:
            print(number)

fizzbuzz()

```
### Test Record 18: `BM2214960def-001` / `BM2214960def`

```python
def fizzbuzz();
 for number in range(1, 101);
 if number % 15 == 0;
 print("FizzBuzz")
 elif number % 3 == 0;
 print("Fizz")
 elif number % 5 == 0;
 print("Buzz")
 else:
    print(number)

    fizzbuzz()
```
### Test Record 19: `BM2214960-002` / `BM2214960`

```python
def fizzbuzz();
 for number in range(1, 101);
 if number % 15 == 0;
 print("FizzBuzz")
 elif number % 3 == 0;
 print("Fizz")
 elif number % 5 == 0;
 print("Buzz")
 else:
    print(number)

    fizzbuzz()
```
### Test Record 20: `IT22277190-001` / `IT22277190`

```python
def fizzbuzz():
    for number in range(1, 101):
        if number % 15 == 0:
            print("FizzBuzz")
        elif number % 3 == 0:
            print("Fizz")
        elif number % 5 == 0:
            print("Buzz")
```
### Test Record 21: `IT22266828-005` / `IT22266828`

```python
def fizzbuzz():
    for number in range(1,100):
        if number % 15 ==0:
            print("Fizzbuzz")
        elif number % 3 ==0:
            
```
### Test Record 22: `IT22267122-001` / `IT22267122`

```python
def fizzbuzz():
    for number in range(1,101):
        if number % 15==0:
            print("FizzBuzz")
        elif number %3==0:
            print("Fizz")
        elif number % 5 == 0:
            print("Buzz")
        else:
            print(number)
```
### Test Record 23: `IT22267122-002` / `IT22267122`

```python
def fizzbuzz():
    for number in range(1,100):
        if number % 15 ==0:
            print("Fizzbuzz")
        elif number % 3 ==0:
            print("Fizz")
```
### Test Record 24: `IT22075758-001` / `IT22075758`

```python
def fizzbuzz():
    for number in range(1, 101):
        if number % 15 ==0:
            print("FizzBuzz")
        elif number % 3 == 0:
            print

```
### Test Record 25: `IT22075758-002` / `IT22075758`

```python
def fizzbuzz():
    for number in range(1,101):
        if number %15 ==0:
            print("FizzBuzz")
        elif number %3==0:
            print("Fizz")
        elif number %5 ==0:
            print ("")
```
### Test Record 27: `IT22221032-001` / `IT22221032`

```python
def fizzbuzz():
    for number in range(1,101):
        if number % 15 == 0:
            print("fizzbuzz")
        elif number % 3 == 0:
            print("Fizz")
        elif number % 5 == 0:
```
### Test Record 28: `IT23736382-001` / `IT23736382`

```python
def fizzbuzz():
   for number in range (1,101):
    if number % 15 ==0;
    print ("FizzBuzz")
    elif number %3 == 0:
        print

```
### Test Record 31: `IT22132550-003` / `IT22132550`

```python
#Python 3
def main():
    name = "BLAIM Student"
    course = "Continuous Authentication"
    print("Hello world")
    print("Hi Sri lanka")
```
### Test Record 32: `IT22138040-002` / `IT22138040`

```python
def fizzbuzz():
    for number in range(1,100)
    if number %5=100:
        print(:Fizzbuzz)
    elif number %3=0:
        print("FIzz")
    
```
### Test Record 33: `IT22266828-006` / `IT22266828`

```python
def fizzbuzz():
    for number in range(1,100):
        if number %5=0:
            print("Fizzbuzz"):
        elif number %3=0:
            print("Fizz")
        elif number %2 =0:
            print("no no")
```
### Test Record 34: `BM2214960-003` / `BM2214960`

```python
def fizzbuzz():
    for number in range(1,100):
        if number %5=0:
            print("fizzbuzz")
        elif number %3 =0:
            print("Fizz")
        elif(number &773723)
```

## Notes for Thesis Use

- `similarity` is the TypeNet-style biometric similarity score returned by `/api/keystroke/verify`; higher values indicate closer match to the enrolled template.
- `risk_score` is generally `1 - similarity` in these records; lower values indicate lower authentication risk.
- For confusion-matrix interpretation, this report follows the saved snapshot assumption: genuine tests are expected to authenticate, and impostor tests are expected not to authenticate.
- `auth_events` and `v_session_risk_summary` represent continuous monitoring timeline checks. Some early/finalized sessions archived zero events because the session buffer had already been cleaned or not populated at finalize time.
- Raw keystroke timing arrays are not expanded here to keep the thesis artifact readable; use the database row IDs and session IDs above to retrieve them if an appendix requires raw event logs.
