# k3s Monitoring Stack

k3s 클러스터의 메트릭·로그·알람 인프라 매니페스트.

## 구성

| 컴포넌트 | 역할 | 형태 |
|---|---|---|
| Prometheus | 메트릭 수집 / 알람 룰 평가 | Deployment |
| Alertmanager | 알람 라우팅 (→ n8n webhook) | Deployment |
| Loki | 로그 저장 | Deployment |
| promtail | 노드 로그 수집 | DaemonSet |
| Grafana | 메트릭·로그 시각화 | Deployment |
| kube-state-metrics | k8s 리소스 상태 메트릭화 | Deployment |
| node-exporter | 노드 OS 메트릭 | DaemonSet |

## 알람 흐름

```
Prometheus → Alertmanager → n8n → AI Agent → WMS 승인 → AAM → SSH 조치
```

## 디렉토리

```
base/         네임스페이스
daemonsets/   node-exporter, promtail
monitoring/   Loki, Prometheus, Alertmanager, Grafana, KSM
```
