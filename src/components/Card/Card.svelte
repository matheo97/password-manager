<script>
</script>

<div class="Card">
  <img class="left-image" src="assets/icon-1.svg" alt="card-icon" />
  <div class="content">
    <span class="title">Dribble</span>
    <span class="email">DaveBriston8055@gmail.com</span>
    <span class="date">Editado ultima vez: <em>24/7/2020 12:30PM</em></span>
  </div>
  <img class="right-image" src="assets/card-icon.svg" alt="" />
</div>

<style>
  .Card {
    width: 335px;
    height: 87px;
    display: flex;
    position: relative;
    justify-content: space-evenly;
    align-items: center;
    background-color: var(--tertiary);
    border-radius: 16px;
    box-shadow: 1px 4px 44px -2px var(--grey);
    margin-top: 23px;
  }

  .Card .content {
    transform: translateX(-10px);
  }

  .Card .content .title {
    font-family: Lato;
    font-style: normal;
    font-weight: 500;
    font-size: 20px;
    line-height: 24px;
    display: block;
  }

  .Card .content .email {
    font-family: Lato;
    font-style: normal;
    font-weight: 500;
    font-size: 14px;
    line-height: 17px;
    color: #747474;
    display: block;
  }

  .Card .content .date {
    font-weight: 500;
    font-size: 12px;
    line-height: 14px;
    color: #898989;
  }

  .Card .content .date em {
    font-size: 12px;
    line-height: 17px;
    color: #747474;
    font-style: normal;
  }

  .Card .right-image {
    position: absolute;
    right: 14.5px;
    top: 13px;
  }
</style>
