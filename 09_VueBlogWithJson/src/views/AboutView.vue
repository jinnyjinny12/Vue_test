<template>
    <div class="about">
      <h1>Jiiny's 오늘의 집 소개 </h1>
      <p>
        이 페이지는 오늘의 집 상품리스트를 정리해놓은 사이트로 오늘의 집에서 사고 싶은 상품들의 이미지와 소개를 저장할 수 있는 입니다!
      </p>
      <ol>
          <li>
            Composition API 기반: Pinia는 Vue 3의 Composition API를 사용하여 상태 관리를 구현합니다. 이를 통해 더 직관적이고 유연한 상태 관리를 할 수 있습니다.
          </li>
          <li>
            간단한 구문: Pinia는 Vuex보다 훨씬 더 간단한 API를 제공합니다. Store를 생성하고 사용하는 과정이 간결하며 직관적입니다.
          </li>
          <li>
            Reactive 상태: Pinia는 Vue 3의 반응성 시스템을 사용하여 상태를 관리합니다. 이를 통해 상태가 변경될 때 자동으로 리렌더링되는 기능을 활용할 수 있습니다.
          </li>
          <li>
            Devtools 통합: Vue Devtools 함께 사용할 수 있어서 상태의 디버깅과 모니터링이 용이합니다.
          </li>
          <li>
            모듈화된 구조: Pinia는 모듈화된 구조를 사용하여 각각의 모듈을 별도로 관리할 수 있습니다. 이를 통해 애플리케이션의 규모가 커져도 코드를 유지하고 관리하기 쉽습니다.
          </li>
          <li>
            TypeScript 지원: Pinia는 TypeScript와 함께 사용할 수 있어서 타입 안정성을 확보할 수 있습니다.
          </li>
      </ol>
    </div>
  </template>
  
  <style>
  .about {
    display: flex;
    justify-content: center;
    flex-direction: column;
    text-align: center;
    border: 1px solid;
    margin-left: auto;
    margin-right: auto;
    margin-top: 2%;
    width: 70%;
  }
  li{
    text-align: left;
    margin-bottom: 1%;
  }
  </style>