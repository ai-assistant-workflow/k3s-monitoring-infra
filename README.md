k3s 클러스터 모니터링 스택

## 구성

- **Prometheus** — 메트릭 수집 / 알람 평가
- **Loki + promtail** — 로그 수집 / 저장
- **Grafana** — 시각화
- **Alertmanager** — 알람 라우팅 (n8n webhook)
- **kube-state-metrics** — k8s 리소스 상태 메트릭
- **node-exporter** — 노드 OS 메트릭 (DaemonSet)
