<template>
    <div class="poster">
        <div class="box">
            <h3>Join Liquidity Bootstrapping <br>Pool (LBP) for Nsure</h3>
            <p>TGE on october <br>28th 11:00 UTC</p>
            <ul>
                <li>
                    <div>
                        <h3>{{days}}</h3>
                        <h4>DAYS</h4>
                    </div>
                </li>
                <li class="point"><span></span><span></span></li>
                <li>
                    <div>
                        <h3>{{hours}}</h3>
                        <h4>HOURS</h4>
                    </div>
                </li>
                <li class="point"><span></span><span></span></li>


                <li>
                    <div>
                        <h3>{{min}}</h3>
                        <h4>MINUTES</h4>
                    </div>
                </li>
                <li class="point"><span></span><span></span></li>


                <li>
                    <div>
                        <h3>{{seconds}}</h3>
                        <h4>SECONDS</h4>
                    </div>
                </li>
            </ul>
            <!--<h4 class="bottom_button">Swap USDC for Nsure Tokens-->
            <!--</h4>-->
            <a href="https://lbp.nsure.network/" target="_Blank" class="bottom_button">Swap USDC for Nsure Tokens</a>
        </div>
    </div>
</template>

<script>
    export default {
        name: "poster",
        data() {
            return {
                days: '--',
                hours: '--',
                min: '--',
                seconds: '--',
                endDate: new Date('2020/10/28 11:00 UTC+0')
            };
        },
        mounted: function () {
            this.countdown();
        },
        methods: {
            countdown() {
                const end = this.endDate.valueOf();
                const now = new Date().valueOf();
                const msec = end - now;
                if (msec < 0) {
                    return this.date_ = `Ended`;
                }
                let day = parseInt((msec / 1000 / 60 / 60 / 24).toString());
                let hr = parseInt((msec / 1000 / 60 / 60 % 24).toString());
                let min = parseInt((msec / 1000 / 60 % 60).toString());
                let sec = parseInt((msec / 1000 % 60).toString());
                this.days = day > 9 ? day : '0' + day;
                this.hours = hr > 9 ? hr : "0" + hr;
                this.min = min > 9 ? min : "0" + min;
                this.seconds = sec > 9 ? sec : "0" + sec;
                this.date_ = `${hr}H ${min}m`;
                setTimeout(() => {
                    this.countdown();
                }, 1000);
            }
        }
    }
</script>
<style lang="less" scoped>
    .poster {
        height: 90vh;
        background-image: url("../assets/images/poster_bg.png");
        background-repeat: no-repeat;
        background-size: 100% 100%;
        background-position: right;
        padding: 0 2%;
        display: flex;
        justify-content: start;
        align-items: center;
        text-transform: uppercase;

        .box {
            top: 0;
            bottom: 0;
            height: 100%;
            display: flex;
            padding: 15% 0 40% 0;
            box-sizing: border-box;
            flex-direction: column;
            margin: auto 0;
            text-align: start;
            align-items: center;
            /*justify-content: space-around;*/
            width: 100%;

            h3 {
                color: white;
                font-size: 17px;
                font-family: "Arial BoldMT";
                font-weight: bold;
                text-align: center;
                line-height: 1.5;



            }

            p {
                font-size: 30px;

                margin: 62px 0 30px 0;
                text-align: center;
                font-family: "ArialMT";
                font-weight: 400;
                color: white;
                box-sizing: border-box;
            }

            ul {
                display: flex;
                align-items: center;
                justify-content: space-around;
                margin-bottom: 62px;
                width: 80%;

                li {

                    div {
                        text-align: center;
                        display: flex;
                        flex-direction: column;
                        align-items: center;
                        justify-content: center;

                        h3 {
                            font-size: 50px;
                            font-weight: bold;
                            color: #13c7fd;
                            line-height: 50px;
                            margin-bottom: 20px;
                        }

                        h4 {

                            font-size: 12px;
                            font-weight: 400;
                            line-height: 1;
                            color: #13c7fd;

                        }
                    }

                }

                .point {
                    display: flex;
                    flex-direction: column;
                    align-items: center;
                    padding-bottom: 32px;
                    box-sizing: border-box;

                    span {
                        display: block;
                        width: 10px;
                        height: 10px;
                        border-radius: 100px;
                        background-color: #13c7fd;
                    }

                    span:last-child {
                        margin-top: 15px;
                    }
                }
            }


            .bottom_button {

                TEXT-DECORATION: none;

                height: 54px;
                margin: 0 auto;
                width: 80%;
                border: 3px #13c7fd solid;
                border-radius: 100px;
                /*box-sizing: border-box;*/


                font-size: 18px;
                font-weight: bold;
                color: #13c7fd;
                line-height: 54px;
                text-align: center;

            }

        }


    }
</style>
