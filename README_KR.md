# things-spinner

## 이는 진행 중인 작업을 표현하기 위한 컴포넌트이며 전역 Event를 제공한다.

## Example 1.Things spinner

``` html
  	<p class="paper-font-subhead">Things spinner</p>
      <demo-snippet class="centered-demo">
        <template>
          <things-spinner id="thingsSpinner"></things-spinner>
          <paper-button color="green" id="spn-button">Toggle Spinner</paper-button>
          <script>
            function toggleSpinner  (e) {
              var spinner = document.querySelector('#thingsSpinner');
              spinner.loading =! spinner.loading;
            };

            var spnButton = document.querySelector('#spn-button');
            spnButton.addEventListener('tap', toggleSpinner);
          </script>        
        </template>
      </demo-snippet>
```

******

## Example 2.Things spinner behavior를 통한 spinner 적용

``` html
      <p class="paper-font-subhead">Things spinner behavior</p>
      <demo-snippet class="centered-demo">
        <template>
          <things-spinner id="thingsSpinner"></things-spinner>
          <paper-button color="green" id="behavior-button">Toggle Spinner</paper-button>
          <script>
            var spnButton = document.querySelector('#behavior-button');
            spnButton.addEventListener('tap', toggleSpinnerWBehavior);
            function toggleSpinnerWBehavior  (e) {
              Things.SpinnerBehavior.toggleSpinner();
            };
          </script>        
        </template>
      </demo-snippet>
  ```

******

## Example 3.Things spinner behavior로 신규 spinner Controller 생성

  ```html
      <p class="paper-font-subhead">Things spinner behavior with custome element</p>
      <demo-snippet class="centered-demo">
        <template>
          <things-spinner id="thingsSpinner"></things-spinner>
          <spinner-controller></spinner-controller>

          <dom-module id="spinner-controller">
            <template>
              <style>
                :host {
                  display: block;
                }
              </style>
              <paper-button color="green"
                            id="behavior-button"
                            on-tap="toggleSpinner">
                  Toggle Spinner
              </paper-button>
            </template>
            <script>
              Polymer({
                is: 'spinner-controller',
                behaviors: [
                  Things.SpinnerBehavior
                ]
              });
            </script>
          </dom-module>
        </template>
      </demo-snippet>
```

*****


## Dependencies

element의 종속성은 [Bower](http://bower.io/)를 통해 관리되며, 아래의 방법을 통해 설치할 수 있다.

    npm install -g bower

다음, element의 종속성을 다운로드한다.

    bower install

## Playing With Your Element

element를 독립적으로 처리하려면 [Polyserve](https://github.com/PolymerLabs/polyserve)를 사용하여 element의 bower 의존성을 유지하도록 하며, 이는 아래의 방법을 통해 설치할 수 있다.

    npm install -g polymer-cli

그리고, 아래의 방법을 통해 실행할 수 있다.

    polymer serve

element를 실행한 경우, `things-spinner`가 디렉토리 이름으로 포함되어 있는 `http://localhost:8080/components/things-spinner/`를 통해 이를 미리 확인할 수 있다. 