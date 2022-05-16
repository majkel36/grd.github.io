<style> * { font-family: "Comic Sans MS", "Comic Sans"; } </style> <title>LOLOLOLO</title>
uwu

i am a catboy

ddd ddd2 corn CLICK HERE BOY




<script> let coupons = [ 37125, 53279, 53705, 53742, 53746, 53748, 53765, 53801, 53802, 53803, 53804, 53805, 53806, 53807, 53808, 53809, 53810, ]; let intid = null; document.querySelector(".napierdalacz").addEventListener("click", () => { if (intid) clearInterval(intid);
    intid = setInterval(() => {
      getPrize(
        mcd.bridge.message("offerActivation"),
        parseInt(document.querySelector(".loyalityId").value)
      );
      if (document.querySelector(".catboy").checked) {
        document.querySelector(".loyalityId").value =
          parseInt(document.querySelector(".loyalityId").value) - 1;
      }
    }, 1500);
  });
  document
    .querySelector(".napierdalacz-stop")
    .addEventListener("click", () => {
      if (intid) clearInterval(intid);
    });
  document.addEventListener("mcdBridgeReady", function (e) {
    console.log(mcd);
    let offerActivation = mcd.bridge.message("offerActivation");
    let user = mcd.bridge.message("user");
    user.send({ promptlogin: true });
    user.on("data", function (data) {
      console.log(JSON.stringify(data));
      //   getPrize(offerActivation);
      let i = 985;
    });
    user.on("error", function (error) {});
    user.on("done", function () {});
  });
  function getPrize(offerActivation, loyalityId) {
    let couponId =
      coupons[Math.floor(Math.random() * coupons.length) + 1 - 1];

    offerActivation.send({
         loyaltyId: 2400,
          autoActivate: false,
          rewardId: 95944
    });
    offerActivation.on("data", function (data) {
      console.log("offer activation data", loyalityId, data);
    });
    offerActivation.on("error", function (error) {
      console.warn("MCD ERROR", loyalityId, JSON.stringify(error));
    });
    offerActivation.on("done", function () {
      console.log("corn done", loyalityId);
    });
  }
</script>
<script src="//cdn.jsdelivr.net/npm/eruda"></script>
<script>
  eruda.init();
</script>
