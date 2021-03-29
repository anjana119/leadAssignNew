<template>
    <div style="background: white !important; height: auto !important;">
        <div class="flex w-full no-gutter justify-center" style="margin-bottom: 100px;">
            <div style="padding-top: 80px; text-align: center;">
                <h1 class="headingFirstOurData">
                    At O2OLead, We Believe in Data Transparency
                </h1>
                <span class="firstPara">
                    It’s not by chance that UpLead is the only sales intelligence tool with a data accuracy guarantee. We believe our data should be transparent for our customers.
                </span>
                <span class="secondPara">
                    This core belief guides how we build our product.
                </span>
                <span class="thirdPara">
                    This core belief guides how we build our product.
                </span>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data() {
            return {};
        }
    }
</script>

<style>
.headingFirstOurData {
    color: #091D30;
    font-family: "Gilroy",Sans-serif;
    font-size: 50px;
    font-weight: 700;
    line-height: 70px;
    width: 60%;
    word-wrap: break-word;
    text-align: center;
    margin-left: auto;
    margin-right: auto;
}
.firstPara {
    color: #69727A;
    font-family: "Gilroy",Sans-serif;
    font-size: 18px;
    font-weight: 500;
    line-height: 27px;
    word-wrap: break-word;
    display: flex;
    width: 70%;
    margin-left: auto;
    margin-right: auto;
    margin-top: 35px;
}
.secondPara {
    color: #69727A;
    font-family: "Gilroy",Sans-serif;
    font-size: 18px;
    font-weight: 500;
    line-height: 27px;
    word-wrap: break-word;
    display: flex;
    width: 70%;
    margin-left: auto;
    margin-right: auto;
    justify-content: center;
    margin-top: 15px;
}
.thirdPara {
    color: #c99ef7;
    text-decoration: underline;
    cursor: pointer;
    font-family: "Gilroy",Sans-serif;
    font-size: 18px;
    font-weight: 500;
    line-height: 27px;
    word-wrap: break-word;
    display: flex;
    width: 70%;
    margin-left: auto;
    margin-right: auto;
    justify-content: center;
    margin-top: 35px;
    margin-bottom: 35px;
}
.thirdPara:hover {
    font-weight: 600;
}
@media only screen and (max-width: 800px) {
    .headingFirstOurData {
        width: 100%;
    }
    .firstPara {
        width: 100%;
    }
    .secondPara {
        width: 100%;
    }
    .thirdPara {
        width: 100%;
    }
}
</style>