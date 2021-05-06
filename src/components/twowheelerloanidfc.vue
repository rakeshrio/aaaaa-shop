<template>
  <div class="col-md-12 m-0 p-0" style="font-family: gilroy">
    <div class="col-md-12 m-0 p-0">
      <img
        src="../assets/bn1.png"
        class=""
        alt=" "
        width="100%"
        height="550px"
      />
    </div>
    <div
      class="m-0 p-0 text-center d-none d-md-block"
      style="
        color: white;
        position: fixed;
        top: 180px;
        right: 0px !important;
        cursor: pointer;
        z-index: 1;
        font-size: 12px;
        letter-spacing: 1px;
        font-family: gilroy;
      "
    >
      <div
        class="col-md-12 m-0 p-3 p-0 border float-button"
        style="background: #4e44d8"
      >
        Buyback
      </div>
      <div
        class="col-md-12 m-0 p-0 py-2 border float-button"
        style="background: #4e44d8"
      >
        loan Against <br />
        Vehicle
      </div>
      <div
        class="col-md-12 m-0 p-0 py-2 border float-button"
        style="background: #4e44d8"
      >
        EMI <br />
        Calculator
      </div>
      <div
        class="col-md-12 m-0 p-0 p-3 py-3 border float-button"
        style="background: #4e44d8"
      >
        Call US
      </div>
      <div
        class="col-md-12 m-0 p-0 p-3 border float-button"
        style="background: #4e44d8"
      >
        Apply Now
      </div>
      <div
        class="col-md-12 m-0 p-0 p-3 border float-button"
        style="background: #4e44d8"
      >
        <i class="fa fa-whatsapp" aria-hidden="true"></i>Whatsapp
      </div>
    </div>
    <div class="col-md-12 m-0 p-0">
      <div
        class="col-md-12 m-0 p-0 py-4 d-none d-md-block"
        style="background: #4e44d8"
      >
        <div class="col-md-8 m-auto p-0">
          <ul
            class="nav nav-pills m-auto justify-content-between"
            style="font-family: Gilroy"
          >
            <li class="nav-item mx-3">
              <a class="nav-link" data-toggle="pill" href="#menu1">Overview</a>
            </li>
            <li class="nav-item mx-3">
              <a class="nav-link" data-toggle="pill" href="#menu2"
                >Fees & Charges</a
              >
            </li>
            <li class="nav-item mx-3">
              <a class="nav-link active" data-toggle="pill" href="#menu3"
                >Eligibility & Documentation</a
              >
            </li>
            <li class="nav-item mx-3">
              <a class="nav-link" data-toggle="pill" href="#menu4"
                >EMI Calculator</a
              >
            </li>
            <li class="nav-item mx-3">
              <a class="nav-link" data-toggle="pill" href="#menu5">FAQs</a>
            </li>
          </ul>
        </div>
      </div>

      <!-- mobile version dropdown -->
      <mobiledropdown></mobiledropdown>

      <!-- Tab panes -->
      <div class="tab-content">
        <div id="menu1" class="container tab-pane">
          <br />
          <div class="col-md-12 mx-0">
            <div class="row">
              <div class="col-12 col-md-5 mt-2 m-0 p-0 overview_sec">
                <h2 class="text-center two_title">Two Wheeler Loan</h2>
                <div class="text-left">
                  <p>
                    If you're in need of a new vehicle, our two wheeler loan is
                    the way to go. We provide you with the opportunity to have
                    the vehicle that you have always dreamed of driving. Our new
                    two wheeler loan comes with an low interest rate and
                    affordable EMIs to help you take your dream bike home today.
                  </p>
                  <p>
                    At Ontrack, we provide special offers for Two Wheeler Loan
                    with ultra-fast processing and minimal documentation.
                  </p>
                </div>
              </div>
              <div class="col-12 col-md-7">
                <img class="img-fluid" src="../assets/poster.png" />
              </div>
            </div>
          </div>

          <div style="font-family: Gilroy" class="row mb-4 m-0 p-0 sect">
            <div class="text-center col-md-3 col-6">
              <img class="img-fluid imgg" src="../assets/Group1.png" />
              <p>Easy<br />Payments</p>
            </div>
            <div class="text-center col-6 col-md-3">
              <img class="img-fluid imgg" src="../assets/Group2.png" />
              <p>Quick<br />Approval</p>
            </div>

            <div class="text-center col-6 col-md-3">
              <img class="img-fluid imgg" src="../assets/Group3.png" />
              <p>Flexible<br />Tenure</p>
            </div>
            <div class="text-center col-6 col-md-3">
              <img class="img-fluid imgg" src="../assets/Group4.png" />
              <p>Affordable<br />EMI</p>
            </div>
            <div class="text-center col-12 col-md-3">
              <img class="img-fluid imgg" src="../assets/Group5.png" />
              <p>Minimum<br />Documentation</p>
            </div>
          </div>

          <div
            class="col-md-12 m-0 p-0"
            style="background: #4e44d8; color: white"
          >
            <h1 class="text-center p-5" style="font-family: gilroyf">
              How It Works
            </h1>
            <div class="col-md-12 row p-0 m-0 text-center">
              <div class="col-md-4 text-center">
                <div class="col-md-12">
                  <img
                    class="img-fluid"
                    src="../assets/scooterpic.png"
                    width="30%"
                    height="auto"
                  />
                  <div class="col-md-12">
                    <h4
                      style="font-weight: ; color: white; font-family: gilroyf"
                    >
                      Choose your <br />
                      vehicle
                    </h4>
                    <p style="font-weight: lighter" class="pip text-center">
                      Select your vehicle sitting at the comfort of your home.
                    </p>
                  </div>
                </div>
              </div>
              <div class="col-md-4">
                <div class="col-md-12">
                  <img
                    class="img-fluid"
                    src="../assets/account.png"
                    width="30%"
                    height="auto"
                  />
                  <div class="col-md-12">
                    <h4
                      style="font-weight: ; color: white; font-family: gilroyf"
                    >
                      Document <br />
                      check
                    </h4>
                    <p style="font-weight: lighter" class="pip text-center">
                      Resale value and downpayment values set by our financial
                      partner
                    </p>
                  </div>
                </div>
              </div>
              <div class="col-md-4">
                <div class="col-md-12">
                  <img
                    class="img-fluid"
                    src="../assets/s.png"
                    width="30%"
                    height="auto"
                  />
                  <div class="col-md-12">
                    <h4
                      style="font-weight: ; color: white; font-family: gilroyf"
                    >
                      Get your <br />
                      dream bike
                    </h4>
                    <p style="font-weight: lighter" class="pip text-center">
                      Get the two wheeler delivered to your home hassle-free!
                    </p>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div id="menu2" class="container tab-pane fade">
          <br />
          <h3 class="my-4" style="font-family: gilroyf; color: #4e44d8">
            Fees & Charges
          </h3>
          <div class="col-md-11 col-12 m-auto p-0">
            <div
              class="col-md-12 m-0 row justify-content-between py-2"
              style="color: white; background: #4e44d8"
            >
              <div>On road price</div>
              <div>Depending on vehicle</div>
            </div>
            <div
              class="col-md-12 m-0 row justify-content-between py-2"
              style=""
            >
              <div>EMI Tenure</div>
              <div>24 - 36 Months</div>
            </div>
            <div
              class="col-md-12 m-0 row justify-content-between py-2"
              style="color: white; background: #4e44d8"
            >
              <div>Downpayment</div>
              <div>10 - 50%</div>
            </div>
            <div
              class="col-md-12 m-0 row justify-content-between py-2"
              style=""
            >
              <div>Stamp Fees</div>
              <div>Rs 100</div>
            </div>
            <div
              class="col-md-12 m-0 row justify-content-between py-2"
              style="color: white; background: #4e44d8"
            >
              <div>Rate of Interest</div>
              <div>13.49%</div>
            </div>
            <div
              class="col-md-12 m-0 row justify-content-between py-2"
              style=""
            >
              <div>Processing Fees</div>
              <div>3%</div>
            </div>
            <div
              class="col-md-12 m-0 row justify-content-between py-2"
              style="color: white; background: #4e44d8"
            >
              <div>NACH Fees</div>
              <div>Rs 500</div>
            </div>

            <div class="text-left mt-3 col-md-12 m-0 p-0">
              <p>Disclaimer:</p>
              <p class="mb-0">
                * The fees/charges indicated above are subject to revision at
                Ontrack's discretion from time to time.
              </p>
              <p>
                * For the definitions of the above charges, please refer below.
              </p>
            </div>

            <div
              class="col-md-12 m-0 py-4 text-left"
              style="color: white; background: #4e44d8"
            >
              <h4 class="mb-4">Definitions:</h4>
              <p class="mb-4">
                On Road price: The On-road Price of a vehicle is the price you
                pay to bring the vehicle from the showroom to the road.
              </p>
              <p class="mb-4">
                Downpayment: A down payment is an initial non-refundable payment
                that is paid upfront for the purchase of a high-priced item.
              </p>
              <p class="mb-4">
                Resale amount: The price which something can achieve when sold
                in the future.
              </p>
              <p class="mb-4">
                EMI: EMI or equated monthly installment, as the name suggests,
                is one part of the equally divided monthly outgoes to clear off
                an outstanding loan within a stipulated time frame.
              </p>
              <p class="mb-4">
                ROI: Rate of Interest; the proportion of a loan that is charged
                as interest to the borrower, typically expressed as an annual
                percentage of the loan outstanding.
              </p>
              <p class="mb-4">
                IRR: Internal rate of return is a method of calculating an
                investment’s rate of return. The term internal refers to the
                fact that the calculation excludes external factors, such as the
                risk-free rate, inflation, the cost of capital, or financial
                risk.
              </p>
              <p class="mb-4">
                Processing Fees: Payment processing fees are the costs that
                dealerships and banks incur when processing payments from
                customers.
              </p>
              <p class="mb-4">
                Nach charges: NACH aims at facilitating electronic Interbank
                High or Low Volume Debit/Credit transactions which are
                repetitive in nature. The banks charge a small fee from the
                customer for this.
              </p>
              <p class="mb-4">
                Stamp charges: Stamp duty is a tax that is levied on single
                property purchases or documents. A physical revenue stamp had to
                be attached to or impressed upon the document to show that stamp
                duty had been paid before the document is legally effective.
              </p>
              <p>
                Tenure: This stands for the agreed loan repayment time-frame
                between the borrower (you) and the lender (bank).
              </p>
            </div>
          </div>
        </div>
        <div id="menu3" class="container tab-pane fade">
          <br />
          <div class="m-0 p-0" v-if="step == 0">
            <h3 class="my-3" style="font-family: gilroyf; color: #4e44d8">
              Eligibility and Documentation
            </h3>
            <p class="py-5 mb-0" style="font-size: 15px">
              The following are the two wheeler loan eligibility criteria for
              salaried and self-employed individuals
            </p>
            <div
              class="col-md-10 px-5 m-auto text-center"
              style="background: #4e44d8; color: white; border-radius: 10px"
            >
              <ul class="col-md-10 py-5 m-auto text-left">
                <li class="mb-3">
                  The applicant’s age must be between 18 to 60 years.
                </li>
                <li class="mb-3">
                  The applicant must have a residential stability for a minimum
                  of one year.
                </li>
                <li>
                  The applicant must have a stable employment status for at
                  least a year.
                </li>
              </ul>
            </div>
            <p class="py-5 mb-0">
              The applicant must submit the following documents to prove their
              two wheeler loan eligibility
            </p>
            <div
              class="col-md-10 px-5 m-auto text-center"
              style="background: #4e44d8; color: white; border-radius: 10px"
            >
              <ul class="col-md-10 py-5 m-auto text-left">
                <li class="mb-3">Identity Proof documents –</li>
                <p style="font-size: 14px">
                  Passport <br />Driving License <br />PAN Card <br />Aadhaar
                  Card <br />Voter’s ID and <br />
                  Recent passport-sized photographs
                </p>
                <li class="mb-3">Income Proof documents (if required) –</li>
                <p class="mb-3" style="font-size: 14px">
                  Latest Income Tax Returns (ITR) for self-employed individuals
                  and <br />
                  Last three months’ Salary Slips/Form 16/Last three months’
                  Bank Statements reflecting salary credits/Salary Certificate
                  for salaried individuals
                </p>
                <li class="mb-3">
                  Last three months’ Bank Statements – mandatory
                </li>
                <li>Residence Ownership Proof – optional</li>
              </ul>
            </div>
            <button
              class="px-5 py-3 my-5"
              @click="step++"
              style="
                color: white;
                background: #4e44d8;
                border: none;
                border-radius: 10px;
                letter-spacing: 1px;
                animation-duration: 1s;
              "
            >
              APPLY NOW
            </button>
          </div>
          <div class="col-md-12" v-if="step == 1">
            <div class="col-md-12 row m-0 p-0">
              <div
                class="col-md-4 m-0 p-0"
                style="font-family: gilroy; color: white"
              >
                <div class="col-md-12 py-5 mr-3" style="background: #4e44d8">
                  <h3 class="mb-5 mt-5" style="font-family: gilroyf">
                    Check your <br />
                    Eligibility
                  </h3>
                  <p class="pt-2 mx-0 px-5 mb-2 mb-0">
                    <a class="pt-2" style="border-bottom: 3.5px solid #ced844"
                      >Mobile Verification</a
                    >
                  </p>
                  <p class="mb-5 mt-5 pt-3">PAN Verification</p>
                  <p class="mb-5 pt-3">Personal Details</p>
                </div>
              </div>
              <div class="col-md-8">
                <div class="col-md-12 py-5" style="background: #e9e8fb">
                  <img src="../assets/Group.png" alt="" />
                  <p class="mb-4 mt-3" style="font-family: gilroyf">
                    Enter Your Mobile Number
                  </p>
                  <div class="row col-md-8 m-auto text-center">
                    <div class="col-md-6 text-center">
                      <input
                        type="text"
                        name=""
                        id=""
                        placeholder="Mobile Number"
                        style=""
                      />
                    </div>
                    <div class="col-md-6">
                      <button class="px-5 btnstyle">verify</button>
                    </div>
                  </div>
                  <p class="my-4" style="font-family: gilroyf">
                    Enter Your OTP
                  </p>
                  <div class="row col-md-8 m-auto text-center">
                    <div class="col-md-6 text-center">
                      <input
                        type="text"
                        name=""
                        id=""
                        placeholder="Mobile Number"
                      />
                    </div>
                    <div class="col-md-6">
                      <button class="px-5 btnstyle" style="" @click="step++">
                        Submit
                      </button>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div class="col-md-12" v-if="step == 2">
            <div class="col-md-12 row m-0 p-0">
              <div
                class="col-md-4 m-0 p-0"
                style="font-family: gilroy; color: white"
              >
                <div class="col-md-12 py-5 mr-3" style="background: #4e44d8">
                  <h3 class="mb-5 mt-5" style="font-family: gilroyf">
                    Check your <br />
                    Eligibility
                  </h3>
                  <p class="pt-2 mx-0 px-5 mb-2 mb-0">Mobile Verification</p>
                  <p class="mb-5 mt-5 pt-3">
                    <a class="pt-2" style="border-bottom: 3.5px solid #ced844"
                      >PAN Verification</a
                    >
                  </p>
                  <p class="mb-5 pt-3">Personal Details</p>
                </div>
              </div>
              <div class="col-md-8">
                <div class="col-md-12 m-0 p-0 py-5" style="background: #e9e8fb">
                  <img class="ml-5" src="../assets/dta.png" alt="" />
                  <p class="mb-4 mt-3" style="font-family: gilroyf">
                    Enter Your PAN Number
                  </p>

                  <div class="col-md-12 m-0 p-0 text-center">
                    <input
                      type="text"
                      class="pr-5 pl-2"
                      name=""
                      id=""
                      placeholder="PAN Number"
                      style=""
                    />
                  </div>

                  <div class="col-md-12 mt-5">
                    <button class="px-5 btnstyle" @click="step++">
                      verify
                    </button>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div class="col-md-12" v-if="step == 3">
            <div class="col-md-12 row m-0 p-0">
              <div
                class="col-md-4 m-0 p-0"
                style="font-family: gilroy; color: white"
              >
                <div class="col-md-12 py-5 mr-3" style="background: #4e44d8">
                  <h3 class="mb-5 mt-5" style="font-family: gilroyf">
                    Check your <br />
                    Eligibility
                  </h3>
                  <p class="pt-2 mx-0 px-5 mb-2 mb-0">Mobile Verification</p>
                  <p class="mb-5 mt-5 pt-3">PAN Verification</p>
                  <p class="mb-5 pt-3">
                    <a class="pt-2" style="border-bottom: 3.5px solid #ced844"
                      >Personal Details</a
                    >
                  </p>
                </div>
              </div>
              <div class="col-md-8">
                <div class="col-md-12  m-0 p-0 py-4">
                  <img src="../assets/personal.png">
                  <div class="col-md-12 m-auto  py-3 text-center">
                    <p style="font-family: gilroyf">Personal Details</p>
                        <div class="col-md-6 d-flex m-auto text-center ml-3 ">
                            
                               <div class="  dropdown-toggle border border-dark"  data-toggle="dropdown">Title</div>
                             
                               <div ><input type="text" class="pr-5" placeholder="Full Name"></div>
                               
                         </div>
                         <div class="col-md-6 d-flex m-auto text-center pt-3 ml-3">
                              
                                   <div><input type="text" class="pr-5" placeholder="Email id"></div>
                                   <div class=" dropdown-toggle border border-dark"  data-toggle="dropdown">.com</div>
                               
  
                          </div>
                          <div class="col-md-6  m-auto pr-5 text-center pt-3 ">
                          <input
                           type="text"
                             class="py-5 pr-5 pl-2"
                              name=""
                            id=""
                            placeholder="442, 9th Main Road,Indiranagar"
                           style=""
                      />
                    </div>
                    <div class="col-md-6 m-auto text-center pr-5 pt-3 ">
                      <input
                        type="text"
                        class="pr-5 pl-2 "
                        name=""
                        id=""
                        placeholder="Bangalore"
                        style=""
                      />
                    </div>
                    <div class="col-md-6 pt-3 pr-5 m-auto text-center">
                      <input
                        type="text"
                        class="pr-5 pl-2"
                        name=""
                        id=""
                        placeholder="Karnataka"
                        style=""
                      />
                    </div>
                    <div class="col-md-6 pt-3 pr-5 m-auto text-center">
                      <input
                        type="text"
                        class="pr-5 pl-2"
                        name=""
                        id=""
                        placeholder="560008"
                        style=""
                      />
                    </div>
                    <h5 class="pt-3 pr-5">Property Status</h5>
                    <div class="container col-md-4 pr-4">
                             <div class="row text-center m-auto">
                                 <div class="col  " style="border:1px solid black">
                                   <img src="../assets/housee.png" class="mt-3" alt="">
                                    <p>Rented</p>
                                   </div>
                                   <div class="col " style="border:1px solid black">
                                     <img src="../assets/home.png" class="mt-3" alt="">
                                     <p>Owned</p>
                                    </div>
                               </div>
                     </div>
                   </div>

                  
                  <div class="col-md-12 mt-4">
                    <button class="px-5 py-2 btnstyle" @click="step++">
                      Submit
                    </button>
                  </div>
                </div>
              </div>
            </div>
          </div>
<div class="col-md-12 mt-5" v-if="step == 4">
  <div class="col-md-12 row m-0 p-0">
            <div
                class="col-md-4 m-0 p-0"
                style="font-family: gilroy; color: white">
                <div class="col-md-12 py-5 mr-3" style="background: #4e44d8">
                  <h3 class="mb-5 mt-5" style="font-family: gilroyf">
                    Check your <br />
                    Eligibility
                  </h3>
                  <p class="pt-2 mx-0 px-5 mb-2 mb-0">Mobile Verification</p>
                  <p class="mb-5 mt-5 pt-3">PAN Verification</p>
                  <p class="mb-5 pt-3">
                    <a class="pt-2" style="border-bottom: 3.5px solid #ced844"
                      >Personal Details</a
                    >
                  </p>
                </div>
              </div>
               <div class="col-md-8">
                 <div class="col-md-12 m-auto  text-center p-0 py-3">
                  <img src="../assets/emp.png">
                    <div class="col-md-6 m-auto text-center pt-3 ">
                      <input
                        type="text"
                        class="pr-5 pl-2 "
                        name=""
                        id=""
                        placeholder="Company's Name"
                        style=""
                      />
                    </div>
                    <div class="col-md-6  m-auto pt-3 text-center">
                          <input
                           type="text"
                             class="py-5 pr-5 pl-2"
                              name=""
                            id=""
                            placeholder="Company's Address"
                           style=""
                      />
                    </div>
                    <div class="col-md-6 m-auto pt-3 align-middle">
                      <input
                        type="text"
                        class="pr-5 pl-2"
                        name=""
                        id=""
                        placeholder="City"
                        style=""
                      />
                    </div>
                    <div class="col-md-6 m-auto text-center pt-3">
                      <input
                        type="text"
                        class="pr-5 pl-2"
                        name=""
                        id=""
                        placeholder="State"
                        style=""
                      />
                    </div>
                    <div class="col-md-6 m-auto text-center pt-3">
                      <input
                        type="text"
                        class="pr-5 pl-2"
                        name=""
                        id=""
                        placeholder="Gross Annual Income"
                        style=""
                      />
                    </div>
                   
                    <h5 class="pt-3">Employment Status</h5>
                    <div class="container col-md-6">
                             <div class="row text-center m-auto" >
                                 <div class="col shadow active" style="border:1px solid black">
                                   <img src="../assets/salary.png" class="mt-3" alt="">
                                    <p>Salaried</p>
                                   </div>
                                   <div class="col shadow" style="border:1px solid black">
                                     <img src="../assets/salaryman.png" class="mt-3" alt="">
                                     <p>Self-Employed</p>
                                    </div>
                               </div>
                     </div>
                   

                  
                  <div class="col-md-12 mt-5">
                    <button class="px-5 py-2 btnstyle" @click="step++">
                      Submit
                    </button>
                  </div>
                </div>






                 </div>

    </div>
</div>


          <div class="col-md-12 mt-5" v-if="step == 5">
            <img
              class="img-fluid"
              src="../assets/thank.png"
              alt=""
              width="400PX"
            />
            <h5 style="font-family: gilroyf">Thank you</h5>
            <p class="mb-0">Your Loan Reference Number is</p>
            <p>LNX123248</p>
            <p>
              Please visit any our listed dealerships and walk out with your
              dream bike. <br />
              Check out our dealerships below
            </p>
          </div>
        </div>
        <div id="menu4" class="container tab-pane fade">
          <br />
          <div class="container emi_calc">
            <h2
              class="text-center"
              style="mb-3;color:#4e44d8;font-weight:bolder"
            >
              EMI Calculator
            </h2>
            <div class="card white_bg mt-2">
              <div class="card-body d-flex flex-row justify-content-between">
                <div>On-road price</div>
                <div class="dropdown drop_btn">
                  <button
                    type="button"
                    class="dropdown-toggle"
                    data-toggle="dropdown"
                  >
                    Select Vehicle
                  </button>
                </div>
              </div>
            </div>

            <div class="card blue_bg" style="background: #4e44d8; color: white">
              <div
                class="card-body d-flex flex-row justify-content-between my-auto"
              >
                <div>Tenure Period</div>
                <div class="dropdown drop_btnn">
                  <button
                    type="button"
                    class="dropdown-toggle"
                    data-toggle="dropdown"
                  >
                    Select months
                  </button>
                </div>
              </div>
            </div>

            <div class="card white_bg">
              <div
                class="card-body d-flex flex-row justify-content-between my-auto"
              >
                <div>Interest</div>
                <div>13.49%</div>
              </div>
            </div>

            <div class="card blue_bg" style="background: #4e44d8; color: white">
              <div
                class="card-body d-flex flex-row justify-content-between my-auto"
              >
                <div>Other Fees</div>
                <div>Rs XXXX</div>
              </div>
            </div>

            <div class="card white_bg">
              <div
                class="card-body d-flex flex-lg-row flex-column justify-content-between my-auto"
              >
                <div>Employment Status</div>
                <div>
                  <input type="radio" id="salaried" value="salaried" />
                  <label class="pr-2 pl-1" for="salaried"> Salaried</label>
                  <input type="radio" id="employed" value="employed" />
                  <label class="pl-1 pr-2" for="employed"> Self-Employed</label>
                </div>
              </div>
            </div>

            <div
              class="card blue_bgg"
              style="background: #4e44d8; color: white"
            >
              <div
                class="card-body d-flex flex-md-row flex-column justify-content-between pt-4"
              >
                <div class="pb-2">Downpayment</div>
                <div class="range pb-2" style="color: white">
                  <div class="field pt-2" style="color: white">
                    <div class="value left">Rs XXXX</div>
                    <input type="range" min="Rs XXXX" max="Rs XXXX" />
                    <div class="value right">Rs XXXX</div>
                  </div>
                </div>
                <div class="input_currency pt-2">
                  <input type="text" placeholder="Amount" /><span
                    style="color: white"
                    >$</span
                  >
                </div>
              </div>
            </div>
            <!-- button -->
            <div class="text-center mt-3">
              <button class="text-center mx-auto check_btnn">SUBMIT</button>
            </div>
          </div>
        </div>
        <div id="menu5" class="container tab-pane fade">
          <br />
          <div class="col-md-12 mx-auto">
            <div
              class="col-md-12 px-5 py-4 mb-3 text-left m-0 p-0"
              style="background: #4e44d8; color: white; border-radius: 10px"
            >
              <p style="font-family: gilroyf">
                What is Ontrack's New Two Wheeler Loan?
              </p>
              <p>
                If you're in need of a new vehicle, our two wheeler loan is the
                way to go. We provide you with the opportunity to have <br />
                the vehicle that you have always dreamed of driving. Our new two
                wheeler loan comes with an low interest rate and affordable EMIs
                to help you take your dream bike home today.
              </p>
            </div>
            <div
              class="col-md-12 px-5 py-4 mb-3 text-left m-0 p-0"
              style="background: #4e44d8; color: white; border-radius: 10px"
            >
              <p style="font-family: gilroyf">
                Why choose Ontrack's New Two Wheeler loan?
              </p>
              <p>Our New Two Wheeler Loan offers the following benefits:</p>
              <p>
                Independence – You don't have to be dependent on public
                transport or anyone else for all your transportation needs. You
                can roam the streets with the vehicle you've always wanted!
              </p>
              <p>
                Hassle-free process – We provide quick processing of your loan
                with minimal documentation. We also provide assistance with RTO
                formalities and multiple repayment methods as per your
                convenience. Apply for Ontrack's New two wheeler loan today!
              </p>
            </div>
            <div
              class="col-md-12 px-5 py-4 mb-3 text-left m-0 p-0"
              style="background: #4e44d8; color: white; border-radius: 10px"
            >
              <p style="font-family: gilroyf">
                How can I be eligible for Ontrack's Two Wheeler Loan?
              </p>
              <p>
                Salaried Professional & Self-Employed over the age of 18 years
                and below 65 years by the end of the tenure.
              </p>
              <p>
                Employment Stability of at least 3 months in case of Salaried
                Professionals & 12 monthd in case of Self-Employed.
              </p>
            </div>
            <div
              class="col-md-12 px-5 py-4 mb-3 text-left m-0 p-0"
              style="background: #4e44d8; color: white; border-radius: 10px"
            >
              <p style="font-family: gilroyf">
                What document do I need for Ontrack's Two Wheeler Loan?
              </p>
              <ul>
                <li>ID Proof</li>
                <li>Address Proof</li>
                <li>Income Proof (if required)</li>
                <li>Bank Statement</li>
              </ul>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// import idfc from '../components/idfcnav'
import mobiledropdown from '../components/mobiledropdown'
export default {
  data() {
    return {
      step: 0,
    };
  },
  components: {
    // idfc
    mobiledropdown
  },
};
</script>

<style scoped>
@font-face {
  font-family: Gilroyf;
  src: url(../assets/font/Gilroy-ExtraBold.otf);
}
@font-face {
  font-family: Gilroy;
  src: url(../assets/font/Gilroy-Light.otf);
}
input {
  text-transform: lowercase;
}

/* two-wheeler loan section styling starts */
.overview_sec {
  width: 1200x;
  margin: auto;
}
.overview_sec > h2 {
  margin-bottom: 3rem;
  font-family: Gilroy;
  font-weight: bolder;
  align-items: center;
  font-size: 65px;
  line-height: 81px;
  color: #4e44d8;
  width: 405px;
}
.overview_sec > p {
  margin-bottom: 10px;
  font-family: Gilroy Light;
  font-weight: lighter;
  font-size: 18px;
}
@media only screen and (max-width: 600px) {
  .overview_sec > h2 {
    font-size: 23px;
    margin-bottom: 1rem;
    width: 313px;
    line-height: 60px;
  }
  .overview_sec > p {
    font-size: 16px;
    margin-bottom: 5px;
  }
}
@media only screen and (min-width: 600px) {
  .overview_sec > h2 {
    font-size: 65px;
    margin-bottom: 2rem;
    width: 405px;
    line-height: 60px;
  }
  .overview_sec > p {
    font-size: 18px;
    margin-bottom: 5px;
    width: 405px;
    line-height: 21px;
    height: 252px;
  }
}
/* two-wheeler loan section ends here */
/* cards styling */
.sect {
  margin-top: 1rem;

  width: 100%;
}
.imgg {
  margin-top: 1rem;
}
/* .tit>p{
  padding-top:1rem;
  font-weight:900;
  margin:auto;
  font-size:26px;
  width:auto;
  font-family:Gilroy;
  margin-bottom:2rem;

} */
@media only screen and (max-width: 600px) {
  .imgg {
    width: 84px;
    padding-top: 1rem;
  }
  .tit > p {
    padding-top: 5px;
    font-weight: 900;
    margin: auto;
    font-size: 18px;
    width: auto;
    font-family: Gilroy ExtraBold;
  }
}
/* ns- - cards styling */
@media (min-width: 768px) {
  .col-md-3 {
    flex: 0 0 25%;
    max-width: 20%;
  }
}

/* cards styling ends*/

/* Last section of overview styling starts */
.last {
  background-color: #4e44d8;
  color: white;
  font-family: Gilroy;
}
.pip {
  font-size: 14px;
  font-weight: lighter;
  font-weight: 200;
  color: #cec5c5;
  text-align: center;
  padding: 5px 5px;
}
@media only screen and (max-width: 600px) {
  .last > h1 {
    font-size: 20px;
  }
  .last > h3 {
    font-size: 10px;
  }
  .pip {
    font-size: 13px;
  }
  .last {
    width: 110px;
    height: 110px;
  }
}

.btnstyle {
  border: none;
  background: #4e44d8;
  border-radius: 5px;
  color: white;
  letter-spacing: 1px;
  font-family: gilroy;
  font-size: 15px;
}
::-webkit-input-placeholder {
  /* Edge */
  text-transform: capitalize;
}

:-ms-input-placeholder {
  /* Internet Explorer 10-11 */
  text-transform: capitalize;
}

::placeholder {
  text-transform: capitalize;
  font-family: gilroy;
}
.nav-pills .nav-link.active {
  background: none !important;
  border-bottom: 3.5px solid #ced844;
  color: white;
  border-radius: 0 !important;
  padding-left: 0;
  padding-right: 0;
  font-weight: 600 !important;
  letter-spacing: 1px;
}
input:focus ~ .floating-label,
input:not(:focus):valid ~ .floating-label {
  top: -7px;
  padding: 0px 5px 0px 5px;
  background-color: #fefefe;
  left: 20px;
  font-size: 11px;
  opacity: 1;
  z-index: 1;
  outline: none !important;
  box-shadow: none !important;
  font-family: gilroy;
}
.form-control {
  border: none !important;
}
textarea:focus ~ .floating-label,
textarea:not(:focus):valid ~ .floating-label {
  top: -7px;
  padding: 0px 5px 0px 5px;
  background-color: #fefefe;
  left: 20px;
  font-size: 11px;
  opacity: 1;
  z-index: 1;
  outline: none !important;
  box-shadow: none !important;
}
select:focus ~ .floating-label,
select:not(:focus):valid ~ .floating-label {
  top: -7px;
  padding: 0px 5px 0px 5px;
  background-color: #fefefe;
  left: 20px;
  font-size: 11px;
  opacity: 1;
  z-index: 1;
  outline: none !important;
  box-shadow: none !important;
}

.inputText {
  outline: none !important;
}
input:focus,
textarea:focus,
select:focus {
  outline: none !important;
  /* box-shadow: none !important;
  color:grey */
}
input {
  font-family: gilroy;
  font-size: 15px;
}
/* .floating-label {
  position: absolute;
  pointer-events: none;
  left: 30px;
  top: 8px;
  transition: 0.2s ease all;
  font-family:gilroy
} */
.float-button:hover {
  opacity: 0.9;
  font-weight: 900;
}
.nav-pills .nav-link {
  background: none !important;
  border-radius: 0 !important;
  padding-left: 0;
  padding-right: 0;
  letter-spacing: 1px;
}
a {
  color: white !important;
}
button:hover {
  opacity: 0.8;
}
button:focus {
  outline: none;
}
border {
  color: black;
}

</style>