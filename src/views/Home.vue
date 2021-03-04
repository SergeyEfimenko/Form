<template>
  <div class="container">
    <form>
      <p>Мой профиль</p>
      <div class="input-field">
        <input
          v-model="formHeader.nameProject"
          type="text"
          id="title"
          class="validate"
          required
        />
        <label for="title">Название проекта*</label>
        <span class="helper-text" data-error="Title is required"></span>
      </div>

      <div class="input-field">
        <input
          v-model="formHeader.author1"
          type="text"
          id="title"
          class="validate"
          required
        />
        <label for="title">Автор*</label>
        <span class="helper-text" data-error="Autor is required"></span>
      </div>

      <!-- <select class="browser-default">
        <option value="" disabled selected>Choose your option</option>
        <option value="1">Option 1</option>
        <option value="2">Option 2</option>
        <option value="3">Option 3</option>
      </select> -->

      <div class="input-field">
        <select>
          <option value="" disabled selected>Choose your option</option>
          <option value="1">Option 1</option>
          <option value="2">Option 2</option>
          <option value="3">Option 3</option>
        </select>
      </div>
      <div class="row">
        <input type="text" ref="datepicker" />
      </div>
    </form>
    <div>
      <h4>{{ formImage.imageTitle }}</h4>

      <form>
        <div class="btn">+ Изображение</div>
        <div class="btn">+ Изображение</div>
        <div class="btn">+ Изображение</div>
        <div class="btn">+ Изображение</div>
        <div class="btn">+ Изображение</div>
      </form>
      <p>{{ formImage.imageText }}</p>
    </div>
    <div>
      <h4>{{ linkOnProject.projectTitle }}</h4>
      <div>
        <input
          v-model="descriptionText"
          placeholder="Вставьте ссылка на проект*"
        />
      </div>
      <div>
        <a href="#">{{ linkOnProject.link }}</a>
      </div>
      <div>
        <a href="#">{{ linkOnProject.link }}</a>
      </div>
    </div>
    <div>
      <h3>{{ descriptionTitle }}</h3>

      <div class="input-field">
        <textarea id="descriptionText" class="materialize-textarea"></textarea>

        <label for="descriptionText"
          >Раскажите детальней про свой концепт*</label
        >
      </div>
      <div>
        <input type="checkbox" />
      </div>
      <div>
        <a class="waves-effect waves-light btn-large">Сохранить</a>
      </div>
      <div>
        <a class="waves-effect waves-light btn-large">Подать заявку</a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Home",
  data: () => ({
    formHeader: {
      nameProject: "",
      author1: "",
      author2: "",
      categories: "",
      creationDate: "",
    },
    formImage: {
      imageTitle: "Добавить изображение*",
      imageText: "Загрузить max 5 изображени, каждое не больше 2мб, только jpg",
    },
    linkOnProject: {
      projectTitle: "Ссылка на проект*",
      linkProject: "",
      link: "www",
    },
    description: {
      descriptionTitle: "Описание концепта",
      descriptionText: "",
    },
  }),
  mounted() {
    M.Chips.init(this.$refs.chips, {
      placeholder: "Task tags",
    });
    M.Datepicker.init(this.$refs.datepicker, {
      format: "dd.mm.yyyy",
      defaultDate: new Date(),
      setDefaultDate: true,
    });
  },
};
</script>


