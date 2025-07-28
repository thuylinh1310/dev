<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>Cậu có muốn đi chơi với Linhh hongg</title>
    <link
      rel="stylesheet"
      href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.0/css/bootstrap.min.css"
    />
    <style>
      .center-screen {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
      }
      img {
        width: 350px;
      }
      .buttones {
        width: 100%;
        text-align: center;
      }
      .btn {
        display: inline-block;
      }
      h2 {
        color: white;
        font-size: 18px;

        padding-top: 2px;
        padding-left: 5px;
        padding-right: 5px;
      }
      .mainn a {
        text-decoration: none;
        position: absolute;
        right: 2%;
        color: red;
        bottom: 2%;
      }
      #nooo {
        background: transparent;
        color: red;
        border: none;
      }
      .nooo {
        color: red;
        font-weight: 700;
        font-size: 25px;
      }
      #nobut {
        background: red;
      }
      #yesbut {
        background: green;
        padding: 10px;
        padding-left: 18px;
        padding-right: 18px;
      }
      h1 {
        text-shadow: 0 0 10px rgba(255, 254, 255, 0.68);
        font-family: cursive;
        font-weight: 800;
      }
    </style>
  </head>
  <body>
    <div
      id="app"
      class="center-screen"
      style="display: flex; flex-direction: column"
    >
    <p style="text-align: center; margin-top: 100px;">nếu thoát ra hoặc không chọn thì là đồng ý đó:)) </p>
     <h1 style="text-align: center; margin-bottom: 20px; font-family: Arial, sans-serif;">Cậu có muốn đi chơi với Linhh hongg?</h1>
      <img
        src="https://raw.githubusercontent.com/DzarelDeveloper/Img/main/Let's%20go.gif"
        alt=""
      />
      <button
        type="button"
        class="btn btn-danger"
        @click="changeText('noButton')"
        id="nooo"
      >
        <h2 class="nooo" @click="changeText('heading') ">
          {{ currentHeaderText }}
        </h2>
      </button>
      <div class="buttones">
        <button
          type="button"
          class="btn btn-success mr-2"
          :style="{ fontSize: yesButtonSize + 'rem' }"
          :key="yesButtonSize"
          @click="yesButton"
          id="yesbut"
        >
          Muốn ạa
        </button>

        <button
          type="button"
          class="btn btn-danger"
          @click="changeText('noButton')"
          id="nobut"
        >
          bận roii
          <h2>No</h2>
        </button>
      </div>
    </div>
    <script src="https://cdn.jsdelivr.net/npm/vue@2"></script>
    <script>
      new Vue({
        el: "#app",
        data: {
          headerText: [
            "",
            "Linh muốn cậu đi cùng với tớ :)",
            "Hãy đi xem cùng nhau cậu nhee",
            "À, đi thôi, cậu mời tớ:))",
            "Chỉ lần này thôi, đi cùng tớ nhaa",
            "Chỉ có chúng ta hai thoii, đc hông?",
            "Tại sao cậu không muốn? tớ mời cậu, đi thoii",
            "Đi thoii, tớ sẽ đến đón cậu ",
            "Đi thôi, đi cùng Linh đi",
            "Tớ muốn cậu đi chơi với tớ",
            "Đi thôi, chúng ta đi cùng nhau, tớ sẽ đến đón cậu",
            "Cậu muốn đi với tớ mà đúng hông tớ bt màa",
            "Chốt nháa, Cậu đi với tớ okk ",
          ],
          confirmationMessages: [
            "Cậu chắc chắn chứ?",
            "Bạn ơi, đừng như vậy chớ?",
            "Tớ muốn gặp cậu á hihih",
          ],
          currentHeaderTextIndex: 0,
          currentConfirmationIndex: 0,
          yesButtonSize: 1,
        },
        methods: {
          changeText(button) {
            if (button === "noButton") {
              this.currentHeaderTextIndex =
                (this.currentHeaderTextIndex + 1) % this.headerText.length;
              this.currentConfirmationIndex =
                (this.currentConfirmationIndex + 1) %
                this.confirmationMessages.length;
              this.yesButtonSize += 5;
            }
          },
          yesButton() {
            window.location.href = "date.html";
          },
        },
        computed: {
          currentHeaderText() {
            return this.headerText[this.currentHeaderTextIndex];
          },
          currentConfirmationText() {
            return this.confirmationMessages[this.currentConfirmationIndex];
          },
        },
      });
    </script>
  </body>
</html>