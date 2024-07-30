
# 그래서 뭐 먹지? 🤔

## 개요

**"그래서 뭐 먹지?"** 프로젝트는 Vue.js 프레임워크를 사용하여 사용자가 특정 지역의 날씨 정보를 기반으로 음식 추천 키워드를 제공해주고, 키워드를 선택하여 음식점을 지도에서 확인할 수 있는 웹 애플리케이션 입니다. 프로젝트는 세 개의 주요 부분으로 구성되어 있는데, 날씨 확인 및 음식 추천 페이지, 지도 페이지, 룰렛을 통한 랜덤 음식 선택 페이지가 있습니다.


#### 미리보기

<img src="https://github.com/user-attachments/assets/0a40f6bc-c44c-4fb8-b246-fca7c65b0658" />

---

### 💡 날씨 확인 및 음식 추천 페이지

1. **지역 입력 및 날씨 정보 로드**
    - 사용자가 검색창에 지역을 입력하면 해당 지역의 실시간 날씨 정보를 불러옵니다.
    - 다양한 형태의 지역 이름(특별시, 광역시, 시, 도, 동 등)을 사용하여 OpenWeather API를 호출해 데이터를 가져옵니다.
    - 날씨 상태에 맞는 애니메이션을 DotLottieVue 라이브러리를 통해 업데이트합니다.
      
2. **추천 메뉴 제공**
    - 불러온 실시간 날씨 정보에 맞춰 어울리는 '추천 메뉴'를 랜덤으로 제공합니다. 각 메뉴는 날씨 상태에 따라 다르게 제안됩니다.
      
3. **지도 페이지로 이동**
    - 사용자가 검색한 위치의 날씨를 기반으로 추천된 메뉴를 클릭하면, 지도 페이지로 이동하여 해당 지역의 음식점을 확인할 수 있습니다.

---

### 💡 지도 페이지

1. **지도 로드 및 장소 검색**
    - `vue3-kakao-maps` API를 사용하여 사용자가 입력한 키워드를 바탕으로 장소를 검색하고, 결과를 지도에 표시합니다.
    - 검색 결과는 사용자가 입력한 키워드 주변의 업체 15곳이 가나다 순서로 정리되어 표시됩니다.
    - 검색 결과를 기반으로 마커를 지도에 표시하고, 사용자와의 상호작용을 위한 기능을 제공합니다.
      
2. **마커 클릭 시 인포윈도우 토글**
    - 지도에 표시된 마커를 클릭하면 해당 장소의 상세 정보를 표시하는 인포윈도우를 토글할 수 있습니다.
      
3. **다양한 키워드 검색**
    - 날씨 페이지에서 선택한 메뉴 외에도 사용자가 직접 입력한 키워드를 바탕으로 장소를 검색하고 결과를 지도에 표시합니다.
      
4. **룰렛 돌리기 페이지 유도**
    - 추천 메뉴에서 선택하지 못한 사용자는 '룰렛 돌리기' 페이지로 유도하여 랜덤으로 키워드를 제공하고 직접 키워드를 추가하여 음식을 선택하도록 합니다. 선택된 메뉴는 지도에서 다시 확인할 수 있습니다.
      
5. **추후 기능**
    - 오버레이에 전화기 아이콘을 추가하여 전화 걸기 기능을 가능하게 구현할 예정입니다.

---

### 💡 룰렛을 통한 랜덤 음식 선택 페이지

#### 미리보기

<img src="https://github.com/user-attachments/assets/ff42389a-177d-43c0-a3db-47752f59d597"  />  

1. **음식 리스트 제공**
    - 미리 저장된 음식 리스트를 기반으로 추천 메뉴를 룰렛 베이스로 제공합니다.
    - 사용자가 직접 메뉴를 추가할 수 있도록 구성되어 있습니다.
      
2. **룰렛 돌리기**
    - 사용자가 직접 입력하거나 선택한 메뉴의 지분은 랜덤으로 구성되어 룰렛을 돌립니다.
    - 룰렛을 여러 번 돌릴 수 있으며, 확정된 결과를 지도 페이지에서 다시 확인할 수 있습니다.
      
3. **결과 확인**
    - 룰렛 결과를 지도 페이지에서 다시 확인할 수 있도록 합니다.
      
4. **메뉴 관리**
    - 메뉴 추가, 삭제, 룰렛 돌리기, 초기화, 지도 보기 등의 핵심 기능을 함수로 구현합니다.

---

### 사용 기술 및 라이브러리

- **프레임워크**: Vue.js
- **언어**: JavaScript, TypeScript
- **스타일링**: CSS, Vuetify
- **애니메이션**: Lottie
- **빌드 도구**: Vite
- **라이브러리**:
    - **Vue Router**: Vue.js의 라우팅 라이브러리
    - **Vuetify**: Vue.js를 위한 UI 라이브러리
    - **vue3-kakao-maps**: Vue 3용 카카오 지도 컴포넌트 라이브러리
    - **@lottiefiles/dotlottie-vue**: Vue.js에서 Lottie 애니메이션을 쉽게 사용할 수 있게 해주는 라이브러리

### 사용 API

- **OpenWeather API**: 사용자가 입력한 지역의 날씨 정보를 제공
- **Kakao Map API**: 카카오 지도를 사용하여 위치 정보를 제공


