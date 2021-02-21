<template>
  <div class="container">
    <h4><br /><b-icon icon="cart"></b-icon> รายการสินค้า</h4>
    <br />

    <div>
      <b-card-group deck>
        <b-card
          id:1
          title="เคสคอม ANTEC CASE DP301M BLACK [RGB]"
          img-src="https://jlgaminggear.com/wp-content/uploads/2020/02/ANTEC-DP301M-1.jpg"
          img-alt="Image"
          img-top
        >
          <b-card-text> 1,590 บาท </b-card-text>
          <template #footer>
            <small class="text-muted">
              <b-button variant="primary" @click="buyClickI1">
                Buy<b-badge variant="light"
                  >{{ BC1 }}<span class="sr-only">unread messges</span></b-badge
                >
              </b-button>
              <b-button variant="danger" @click="cancel1">
                Cancel
              </b-button></small
            >
          </template>
        </b-card>

        <b-card
          id:2
          title="CORSAIR CASE ICUE 220T RGB [WHITE]"
          img-src="https://jlgaminggear.com/wp-content/uploads/2020/06/CORSAIR-220T-RGB-WHITE-1.jpg"
          img-alt="Image"
          img-top
        >
          <b-card-text> 3,690 บาท </b-card-text>
          <template #footer>
            <small class="text-muted"
              ><b-button variant="primary" @click="buyClickI2">
                Buy<b-badge variant="light"
                  >{{ BC2 }}<span class="sr-only">unread messges</span></b-badge
                >
              </b-button>
              <b-button variant="danger" @click="cancel2">
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
          <b-card-text> 990 บาท </b-card-text>
          <template #footer>
            <small class="text-muted"
              ><b-button variant="primary" @click="buyClickI3">
                Buy<b-badge variant="light"
                  >{{ BC3 }}<span class="sr-only">unread messges</span>
                </b-badge>
              </b-button>
              <b-button variant="danger" @click="cancel3"> Cancel </b-button>
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
          <b-card-text> 3,590 บาท </b-card-text>
          <template #footer>
            <small class="text-muted"
              ><b-button variant="primary" @click="buyClickI4">
                Buy<b-badge variant="light"
                  >{{ BC4 }}<span class="sr-only">unread messges</span></b-badge
                >
              </b-button>
              <b-button variant="danger" @click="cancel4">
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
          <b-card-text> 890 บาท </b-card-text>
          <template #footer>
            <small class="text-muted"
              ><b-button variant="primary" @click="buyClickI5">
                Buy<b-badge variant="light"
                  >{{ BC5 }}<span class="sr-only">unread messges</span></b-badge
                >
              </b-button>
              <b-button variant="danger" @click="cancel5">
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
          <b-card-text> 3,090 บาท </b-card-text>
          <template #footer>
            <small class="text-muted"
              ><b-button variant="primary" @click="buyClickI6">
                Buy<b-badge variant="light"
                  >{{ BC6 }}<span class="sr-only">unread messges</span></b-badge
                >
              </b-button>
              <b-button variant="danger" @click="cancel6">
                Cancel
              </b-button></small
            >
          </template>
        </b-card>
      </b-card-group>
    </div>
    <br /><br />
    <div class="row">
      <div class="col-sm-8"></div>
      <div class="col-sm-3">
        <div class="card" style="width: 18rem">
          <div class="card-body">
            <h5 class="card-title">
              <h3>Total = {{ BC7 }} บาท</h3>
              <b-button
                variant="success"
                v-on:click="say"
                @click="CancelAllItem"
                >จ่ายเงิน</b-button
              >

              <b-button variant="danger" @click="CancelAllItem">
                ยกเลิกการซื้อทั้งหมด
              </b-button>
            </h5>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      BC1: 0,
      BC2: 0,
      BC3: 0,
      BC4: 0,
      BC5: 0,
      BC6: 0,
      BC7: 0,
    };
  },
  methods: {
    say: function () {
      if (this.BC7 != 0) {
        alert("ขอบคุณที่ใช้บริการ");
      } else if (this.BC7 <= 0) {
        alert("ท่านต้องเลือกสินค้าสินค้าก่อนชำระเงิน");
      }
    },
    buyClickI1() {
      this.BC1++;
      this.BC7 += 1590;
    },
    buyClickI2() {
      this.BC2++;
      this.BC7 += 3690;
    },
    buyClickI3() {
      this.BC3++;
      this.BC7 += 990;
    },
    buyClickI4() {
      this.BC4++;
      this.BC7 += 3590;
    },
    buyClickI5() {
      this.BC5++;
      this.BC7 += 890;
    },
    buyClickI6() {
      this.BC6++;
      this.BC7 += 3090;
    },
    cancel1() {
      if (this.BC1 > 0) {
        this.BC1--;
        this.BC7 -= 1590;
      }
    },
    cancel2() {
      if (this.BC2 > 0) {
        this.BC2--;
        this.BC7 -= 3690;
      }
    },
    cancel3() {
      if (this.BC3 > 0) {
        this.BC3--;
        this.BC7 -= 990;
      }
    },
    cancel4() {
      if (this.BC4 > 0) {
        this.BC4--;
        this.BC7 -= 3590;
      }
    },
    cancel5() {
      if (this.BC5 > 0) {
        this.BC5--;
        this.BC7 -= 890;
      }
    },
    cancel6() {
      if (this.BC6 > 0) {
        this.BC6--;
        this.BC7 -= 3090;
      }
    },
    CancelAllItem() {
      if (this.BC7 > 0) {
        (this.BC1 = 0),
          (this.BC2 = 0),
          (this.BC3 = 0),
          (this.BC4 = 0),
          (this.BC5 = 0),
          (this.BC6 = 0),
          (this.BC7 = 0);
      }
    },
  },
};
</script>