<template>
  <div class="container">
    <form id="form" ref="document">
      <div class="content">
        <HeaderComponent />
        <h3 style="margin-bottom: 70px">FIXED TERM AGREEMENT</h3>
        <p class="between">between</p>

        <div class="bmf">
          <h3>BMF ATTORNEYS</h3>
          <p>with company registration number 2022/123456/07</p>
        </div>

        <p class="and">and</p>
        <div class="clientname">
          <input
            style="
              height: 20px;
              outline: none;
              border: none;
              border-bottom: 1px solid black;
            "
            type="text"
            v-model="clientName"
            placeholder="INSERT CLIENT NAME"
          />
        </div>
        <p style="margin-bottom: 200px">
          Collectively referred herein as the “parties”
        </p>

        <div class="html2pdf__page-break"></div>
        <HeaderComponent />

        <ol style="font-weight: bold">
          <li>
            <span style="padding-left: 25px">Payment Terms</span>

            <ul type="disc" class="payment-details" style="font-weight: normal">
              <li>
                BMF Attorney’s fee
                <input
                  style="
                    height: 20px;
                    outline: none;
                    border: none;
                    border-bottom: 1px solid black;
                  "
                  type="text"
                  v-model="paymentAmount"
                  placeholder="Insert Payment Amount"
                />
                (excluding VAT). The retainer fee can be paid upfront, or
                month-to-month and the payment terms can be payable as follows:

                <ul class="circled">
                  <li>
                    Upfront
                    <ul>
                      <li>
                        Three-twelfths of the fee during the probation period in
                        3 equal instalments by the 7th day of each month
                      </li>
                      <li>
                        Nine-twelfths of the fee upon conclusion of the
                        probation period of employment payable on the 7th day of
                        the 4th month
                      </li>
                    </ul>
                  </li>
                  <li>
                    Month-to-month
                    <ul>
                      <li>
                        The month-to-month fee shall be paid by the 7th day of
                        each month
                      </li>
                    </ul>
                  </li>
                </ul>
              </li>
              <li>
                No variation or amendment to this Agreement shall be of any
                effect unless such amendment is put in writing and signed by all
                parties
              </li>
              <li>
                Any documentation prepared by
                <span style="font-weight: bold">BMF Attorneys</span> remains its
                property
              </li>
            </ul>
          </li>
          <li style="margin-top: 30px">
            <span style="padding-left: 25px">Appointment</span>

            <ul class="appointment">
              <li
                class="list-items"
                style="margin-top: 15px; font-weight: normal"
              >
                <p
                  style="
                    margin-bottom: 0;
                    margin-right: 15px;
                    font-weight: bold;
                  "
                >
                  2.1
                </p>
                <p style="margin-bottom: 0">
                  The Client has procured the services of
                  <span style="font-weight: bold">BMF Attorneys</span>
                  and hereby accepts the appointment as an independent
                  contractor of the Client for a fixed period of time
                </p>
              </li>
              <li style="font-weight: normal" class="list-items">
                <p style="margin-right: 15px; margin-top: 0; font-weight: bold">
                  2.2
                </p>
                <p style="margin-top: 0">
                  The reason for this fixed-term contract is
                  <span style="font-weight: bold">
                    for the appointment and completion of the
                  </span>
                  <input
                    style="
                      height: 20px;
                      outline: none;
                      border: none;
                      border-bottom: 1px solid black;
                    "
                    type="text"
                    v-model="serviceDesc"
                    placeholder="Service Description"
                  />
                </p>
              </li>
            </ul>
          </li>
          <li style="margin-top: 0px">
            <span style="padding-left: 25px">Duration</span>
            <ul style="list-style: none">
              <li class="list-items">
                <p style="margin-top: 12px; margin-right: 15px">3.1</p>
                <p style="font-weight: normal; margin-top: 12px">
                  Notwithstanding the date of signature hereof, this fixed term
                  contract shall be deemed to have commenced on the
                  <input
                    style="height: 15px; outline: none; font-weight: bold"
                    type="date"
                    v-model="startDate"
                    placeholder="Enter Start Date"
                  />
                  and will terminate, without further notice, on the
                  <input
                    style="height: 15px; outline: none; font-weight: bold"
                    type="date"
                    v-model="endDate"
                    placeholder="Enter End Date"
                  />
                </p>
              </li>
              <li class="list-items" style="font-weight: normal">
                <p style="margin-top: 0px; margin-right: 15px">3.2</p>
                <p style="margin-top: 0px">
                  The automatic termination of the contract on the Termination
                  Date shall not be construed as a dismissal but as the
                  completion of a fixed term contract.
                </p>
              </li>
            </ul>
          </li>
        </ol>

        <div class="html2pdf__page-break"></div>
        <HeaderComponent></HeaderComponent>

        <p style="font-weight: bold">4.</p>
        <div style="margin-top: 30px">
          <div class="signedat">
            <p style="width: 50%">Signed at</p>
            <p style="width: 50%">on</p>
          </div>
          <hr
            style="
              background-color: black;
              margin-bottom: 0;
              width: 40%;
              float: left;
              height: 1px;
            "
          />
          <br />
          <p style="margin-top: 0; margin-bottom: 60px">
            Who warrants authority on behalf of Jobox
          </p>
          <div class="signedat">
            <p style="width: 50%">Signed at</p>
            <p style="width: 50%">on</p>
          </div>
          <hr
            style="
              background-color: black;
              margin-bottom: 0;
              width: 40%;
              float: left;
              height: 1px;
            "
          />
          <br />
          <p style="margin-top: 0; margin-bottom: 60px">
            Who warrants authority on behalf of
          </p>
        </div>
      </div>
    </form>
    <p v-if="err" style="background-color: red;color: white; " >Please Enter All Required Fields</p>
    <p v-if="dates" style="background-color: red;color: white; " >Start date must be smaller than end date</p>
    <button @click="exportToPDF">Save and Export to PDF</button>
    <br />
    <br />
    <br />
    <br />
  </div>
</template>

<script>
import HeaderComponent from "./HeaderComponent.vue";
import html2pdf from "html2pdf.js";

export default {
  name: "FormComponent",
  components: {
    HeaderComponent,
  },
  data() {
    return {
      clientName: "",
      paymentAmount: "",
      serviceDesc: "",
      startDate: "",
      endDate: "",
      err: false,
      dates: false
    };
  },
  methods: {
    exportToPDF() {
      if (
        this.clientName &&
        this.paymentAmount &&
        this.serviceDesc &&
        this.startDate &&
        this.endDate
      ) {
        if(this.startDate > this.endDate){
          this.dates = true;
          this.err = false;
        }
        else{
          html2pdf(this.$refs.document, {
            margin: [0, 0.5, 0, 0.5],
            filename: "document.pdf",
            image: { type: "jpeg", quality: 0.98 },
            html2canvas: { dpi: 192, letterRendering: true },
            jsPDF: { unit: "in", format: "a4", orientation: "portrait" },
          });
          this.err = false
          this.dates = false
        }
      } else {
        this.err = true
      }
    },
  },
};
</script>

<style scoped>
.container {
  display: grid;
  justify-content: center;
  color: black;
  /* padding: 0 30px; */
}

#form {
  background-color: #fff;
  width: 670px;
  padding: 0 10px;
  padding-left: 5px;
}
.content {
  padding-left: 5px;
}
.between {
  margin-bottom: 30px;
}
.bmf {
  text-align: center;
  font-weight: bold;
}
.and {
  margin: 45px 0;
}
.clientname {
  display: grid;
  justify-content: center;
  margin-bottom: 70px;
}
.payments {
  display: flex;
  font-weight: bold;
  margin-bottom: 0;
  padding-bottom: 0;
}
.payment-details {
  padding-top: 0;
  margin-top: 10px;
  display: grid;
  justify-content: center;
  /* list-style: none; */
}
.payment-details li {
  width: 95%;
  line-height: 1.9;
}
.circled {
  list-style: circle;
}
/* .circled li:before {
  content: "o";
  font-size: 11pt;
} */
.appointment {
  list-style: none;
}
.appointment li {
  width: 87%;
}

ol {
  counter-reset: item;
}
ol > li {
  display: block;
}
ol > li:before {
  content: counters(item, ".") ". ";
  counter-increment: item;
}
ul .list-items {
  display: flex;
}
.signedat {
  display: flex;
  font-weight: normal;
  margin: 75px 0;
}
/* li:before{ content:'\00b7'; font-size:50px; } */
</style>
