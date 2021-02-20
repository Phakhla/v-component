<template>
  <div class="container">
    <h4>
      <br><b-icon icon="cart"></b-icon>รายการสินค้า<b-icon icon="cart"></b-icon>
    </h4><br>
    <div>
      <b-card-group deck>
        <b-card
          id:1
          title="เคสคอม ANTEC CASE DP301M BLACK [RGB]"
          img-src="https://jlgaminggear.com/wp-content/uploads/2020/02/ANTEC-DP301M-1.jpg"
          img-alt="Image"
          img-top
        >
          <b-card-text>
            1,590 บาท
          </b-card-text>
          <template #footer>
            <small class="text-muted">
              <b-button variant="warning" @click="buyClickI1">
                Buy<b-badge variant="light"
                  >{{ buyClick1
                  }}<span class="sr-only">unread messges</span></b-badge
                >
              </b-button>
              <b-button variant="danger" @click="CancelItem1">
                Cancel
              </b-button></small
            >
          </template>
        </b-card>

        <b-card
          id:2
          title="NUBWO CASE NPC-315 QUASAR (BLACK)"
          img-src="https://jlgaminggear.com/wp-content/uploads/2019/09/1-72-300x300.jpg"
          img-alt="Image"
          img-top
        >
          <b-card-text>
            1,490 บาท
          </b-card-text>
          <template #footer>
            <small class="text-muted"
              ><b-button  @click="buyClickI2">
                Buy<b-badge variant="light"
                  >{{ buyClick2
                  }}<span class="sr-only">unread messges</span></b-badge
                >
              </b-button>
              <b-button variant="danger" @click="CancelItem2">
                Cancel
              </b-button></small
            >
          </template>
        </b-card>

        <b-card
          id:3
          title="AERCOOL CASE GLIDER [RGB]"
          img-src="https://jlgaminggear.com/wp-content/uploads/2020/06/Aercool-Glider-1.jpg"
          img-alt="Image"
          img-top
        >
          <b-card-text>
            990 บาท
          </b-card-text>
          <template #footer>
            <small class="text-muted"
              ><b-button variant="warning" @click="buyClickI3">
                Buy<b-badge variant="light"
                  >{{ buyClick3 }}<span class="sr-only">unread messges</span>
                </b-badge>
              </b-button>
              <b-button variant="danger" @click="CancelItem3">
                Cancel
              </b-button>
            </small>
          </template>
        </b-card>
      </b-card-group>
    </div>
    <div>
      <b-card-group deck>
        <b-card
          id:4
          title="GREATWALL T1 ZERO"
          img-src="https://jlgaminggear.com/wp-content/uploads/2020/08/2279.jpg"
          img-alt="Image"
          img-top
        >
          <b-card-text>
            3,590 บาท
          </b-card-text>
          <template #footer>
            <small class="text-muted"
              ><b-button variant="warning" @click="buyClickI4">
                Buy<b-badge variant="light"
                  >{{ buyClick4
                  }}<span class="sr-only">unread messges</span></b-badge
                >
              </b-button>
              <b-button variant="danger" @click="CancelItem4">
                Cancel
              </b-button></small
            >
          </template>
        </b-card>

        <b-card
          id:5
          title="NUBWO CASE NPC-320 HORIZON (BLACK)"
          img-src="https://jlgaminggear.com/wp-content/uploads/2019/09/1-75.jpg"
          img-alt="Image"
          img-top
        >
          <b-card-text>
            890 บาท
          </b-card-text>
          <template #footer>
            <small class="text-muted"
              ><b-button variant="warning" @click="buyClickI5">
                Buy<b-badge variant="light"
                  >{{ buyClick5
                  }}<span class="sr-only">unread messges</span></b-badge
                >
              </b-button>
              <b-button variant="danger" @click="CancelItem5">
                Cancel
              </b-button></small
            >
          </template>
        </b-card>
        <b-card
          id:6
          title="NZXT CASE H210 [WHITE]"
          img-src="https://jlgaminggear.com/wp-content/uploads/2020/02/NZXT-CASE-H210-WHITE-1.jpg"
          img-alt="Image"
          img-top
        >
          <b-card-text>
            3,090 บาท
          </b-card-text>
          <template #footer>
            <small class="text-muted"
              ><b-button variant="warning" @click="buyClickI6">
                Buy<b-badge variant="light"
                  >{{ buyClick6
                  }}<span class="sr-only">unread messges</span></b-badge
                >
              </b-button>
              <b-button variant="danger" @click="CancelItem6">
                Cancel
              </b-button></small
            >
          </template>
        </b-card>
      </b-card-group>
    </div>
    <h1>ราคาทั้งหมด = {{ buyClick7 }} บาท</h1>

    <b-button variant="success"  v-on:click="say" @click="CancelAllItem"
      >จ่ายเงิน</b-button
    >

    <b-button variant="danger" @click="CancelAllItem">
      ยกเลิกการซื้อทั้งหมด
    </b-button><br><br>
  </div>
</template>
<script>
export default {
  data() {
    return {
      buyClick1: 0,
      buyClick2: 0,
      buyClick3: 0,
      buyClick4: 0,
      buyClick5: 0,
      buyClick6: 0,
      buyClick7: 0
    };
  },
  methods: {
    say: function() {
      if (this.buyClick7 != 0) {
        alert(
          "ขอบคุณที่ใช้บริการ สินค้าที่คุณลูกค้าสั่งนั้นจะถูกจัดส่งให้ในเร็วๆนี้ กรุณาตรวจสอบสินค้าของท่านด้วย ปล.ไม่สามารถคือสินค้าได้นะอิอิ"
        );
      } else if (this.buyClick7 <= 0) {
        alert("ท่านต้องเลือกสินค้าสินค้าก่อนชำระเงินนะ");
      }
    },
    buyClickI1() {
      this.buyClick1++;
      this.buyClick7 += 1590;
    },
    buyClickI2() {
      this.buyClick2++;
      this.buyClick7 += 1490 ;
    },
    buyClickI3() {
      this.buyClick3++;
      this.buyClick7 += 990;
    },
    buyClickI4() {
      this.buyClick4++;
      this.buyClick7 += 3590;
    },
    buyClickI5() {
      this.buyClick5++;
      this.buyClick7 += 890;
    },
    buyClickI6() {
      this.buyClick6++;
      this.buyClick7 += 3090;
    },
    CancelItem1() {
      if (this.buyClick1 > 0) {
        this.buyClick1--;
        this.buyClick7 -= 1590;
      }
    },
    CancelItem2() {
      if (this.buyClick2 > 0) {
        this.buyClick2--;
        this.buyClick7 -= 1490 ;
      }
    },
    CancelItem3() {
      if (this.buyClick3 > 0) {
        this.buyClick3--;
        this.buyClick7 -= 990;
      }
    },
    CancelItem4() {
      if (this.buyClick4 > 0) {
        this.buyClick4--;
        this.buyClick7 -= 3590;
      }
    },
    CancelItem5() {
      if (this.buyClick5 > 0) {
        this.buyClick5--;
        this.buyClick7 -= 890;
      }
    },
    CancelItem6() {
      if (this.buyClick6 > 0) {
        this.buyClick6--;
        this.buyClick7 -= 3090;
      }
    },
    CancelAllItem() {
      if (this.buyClick7 > 0) {
        (this.buyClick1 = 0),
          (this.buyClick2 = 0),
          (this.buyClick3 = 0),
          (this.buyClick4 = 0),
          (this.buyClick5 = 0),
          (this.buyClick6 = 0),
          (this.buyClick7 = 0);
      }
    }
  }
};
</script>