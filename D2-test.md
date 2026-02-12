# D2 다이어그램 테스트: User → Azure WAF → AKS POD

## 렌더링 결과

![User → Azure WAF → AKS POD](diagrams/D2-test.svg)

## 테스트 결과

| 항목 | 결과 |
|------|------|
| 다이어그램 | User → Azure WAF → AKS POD |
| 테마 | `flagship_terrastruct` (Azure 자동 감지) |
| 애니메이션 | `style.animated: true` (트래픽 흐름 자동 감지) |
| 아이콘 | WAF, AKS 공식 Azure 아이콘 적용 |
| 워터마크 | `🐾 보리가 작성한 다이어그램` (우측 하단) |
| 출력 파일 | `workspaces/diagrams/D2-test.svg` (51KB) |

## D2 소스 코드

```d2
direction: right

user: User {
  shape: person
  style.fill: "#E3F2FD"
  style.stroke: "#1565C0"
  style.font-size: 16
}

waf: Azure WAF {
  icon: https://raw.githubusercontent.com/benc-uk/icon-collection/master/azure-icons/Web-Application-Firewall-Policies(WAF).svg
  shape: hexagon
  style.fill: "#FFF3E0"
  style.stroke: "#E65100"
  style.font-size: 14
}

aks: AKS Cluster {
  icon: https://raw.githubusercontent.com/benc-uk/icon-collection/master/azure-icons/Kubernetes-Services.svg
  style.fill: "#E8F5E9"
  style.stroke: "#2E7D32"

  pod: Application POD {
    shape: rectangle
    style.fill: "#C8E6C9"
    style.stroke: "#388E3C"
    style.font-size: 12
  }
}

user -> waf: HTTPS Request {
  style.animated: true
  style.stroke: "#FF6F00"
  style.font-size: 12
}

waf -> aks.pod: Filtered Traffic {
  style.animated: true
  style.stroke: "#2E7D32"
  style.font-size: 12
}
```

## 구현된 기능

### 1. Blob Storage 아이콘 동적 조회
- `list_azure_blob_icons` 도구로 `stgborivault` Blob Storage에서 아이콘 검색 가능
- 하드코딩된 `AZURE_ICON_MAP` (115개) 외 추가 아이콘 활용

### 2. 워터마크
- `🐾 보리가 작성한 다이어그램` 텍스트가 우측 하단에 자동 삽입
- `watermark: false` 파라미터로 비활성화 가능

### 3. 스마트 자동 판단
- Azure 서비스 감지 → `flagship_terrastruct` 테마 자동 선택
- 트래픽/흐름 감지 → 애니메이션 안내 자동 포함


> Updated by Bori AI Agent
