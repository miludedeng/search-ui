<template>
<div id="app">
    <div class="searchbox-wrapper">
        <div class="container">
            <div class="row">
                <div class="col-lg-12 col-md-12 col-sm-12">
                    <div class="search-result-wrapper">
                        <div class="big-search">

                            <ul class="search-tags-wrapper">
                                <li class="s-field" style="width: 1090px;">
                                    <input type="text" class="form-control global-input" id="search-autocomplete" v-model="searchKey" name="q" autocomplete="off" value="">
                                </li>
                            </ul>
                            <a onclick="alert(1)" class="search-btn"><i class="big-search-icon"></i></a>
                            <a @click="cancelSearchInput" v-show="isCancelShow"><i class="cancel-icon"></i></a>
                        </div>
                        <div class="search-nav-auto-complete">
                            <div class="autocomplete-suggestions" v-show="showSuggest" style="position: absolute; max-height: 300px; z-index: 99999; opacity: 1; ; top: 80px; left: 45px; width: 1066px;">
                                <li class="autocomplete-suggestion" v-for="suggest in suggests" data-index="0" @click="choseSuggest"><span class="cursor-pointer">{{suggest}}<em></em></span></li>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
    <div class="container">
        <div class="row">
            <div class="col-lg-12 col-md-12 col-sm-12">
                <div class="sorting-tabs-wrapper m-t-40">
                    <div class="bdr-btm m-b-30 clearfix">
                        <div class="pull-right">
                            <p class="search-count">为你查询到 {{total}} 条结果</p>
                        </div>
                    </div>
                    <div class="sorting-tab-content">
                        <div class="row">
                            <div class="col-lg-9 col-md-9 col-sm-9 col-xs-12">
                                <div class="tab-nav">
                                    <ul id="classify-tab" class="nav nav-tabs classify-tab">
                                        <li class="active"><a href="#home" data-toggle="tab">中图</a></li>
                                        <li><a href="#ios" data-toggle="tab">学科</a></li>
                                        <li><a href="#ios" data-toggle="tab">地区</a></li>
                                        <li><a href="#ios" data-toggle="tab">年份</a></li>
                                        <li><a href="#ios" data-toggle="tab">作者</a></li>
                                        <li><a href="#ios" data-toggle="tab">行业</a></li>
                                    </ul>
                                    <div id="classify-list" class="tab-content classify-list">
                                        <div class="tab-pane fade in active" id="home">
                                            <ul>
                                                <ol v-for="classify in classifies">{{classify}}</ol>
                                            </ul>
                                        </div>
                                        <div class="tab-pane fade" id="ios">
                                            <ul>
                                                <ol v-for="classify in classifies">{{classify}}</ol>
                                            </ul>
                                        </div>
                                        <div class="tab-pane fade" id="ios">
                                            <ul>
                                                <ol v-for="classify in classifies">{{classify}}</ol>
                                            </ul>
                                        </div>
                                        <div class="tab-pane fade" id="ios">
                                            <ul>
                                                <ol v-for="classify in classifies">{{classify}}</ol>
                                            </ul>
                                        </div>
                                        <div class="tab-pane fade" id="ios">
                                            <ul>
                                                <ol v-for="classify in classifies">{{classify}}</ol>
                                            </ul>
                                        </div>
                                        <div class="tab-pane fade" id="ios">
                                            <ul>
                                                <ol v-for="classify in classifies">{{classify}}</ol>
                                            </ul>
                                        </div>
                                    </div>
                                </div>
                                <div id="tab1" class="tab active m-b-40 m-t-40 result-list">
                                    <ul>
                                        <li>
                                            <!-- <p class="section-col"></p> -->
                                            <h4><a href="/guide/en/elasticsearch/reference/5.3/search-request-sort.html">葡语国家与“<font color="#FF0000">一带一路</font>”的新走廊建设</a></h4>
                                            <p>“一带一路”的构想具有开放性和包容性。本文主要论证葡语国家形成了一条独特的经济文化走廊。从地理分布的特点来看，这一历史原因形成的经济文化走廊有别于传统意义上的陆路走廊，海洋是连接各个葡语...</p>
                                        </li>
                                        <li>
                                            <!-- <p class="section-col"></p> -->
                                            <h4><a href="/guide/en/elasticsearch/reference/5.3/search-request-sort.html">葡语国家与“<font color="#FF0000">一带一路</font>”的新走廊建设</a></h4>
                                            <p>“一带一路”的构想具有开放性和包容性。本文主要论证葡语国家形成了一条独特的经济文化走廊。从地理分布的特点来看，这一历史原因形成的经济文化走廊有别于传统意义上的陆路走廊，海洋是连接各个葡语...</p>
                                        </li>
                                        <li>
                                            <!-- <p class="section-col"></p> -->
                                            <h4><a href="/guide/en/elasticsearch/reference/5.3/search-request-sort.html">葡语国家与“<font color="#FF0000">一带一路</font>”的新走廊建设</a></h4>
                                            <p>“一带一路”的构想具有开放性和包容性。本文主要论证葡语国家形成了一条独特的经济文化走廊。从地理分布的特点来看，这一历史原因形成的经济文化走廊有别于传统意义上的陆路走廊，海洋是连接各个葡语...</p>
                                        </li>
                                        <li>
                                            <!-- <p class="section-col"></p> -->
                                            <h4><a href="/guide/en/elasticsearch/reference/5.3/search-request-sort.html">葡语国家与“<font color="#FF0000">一带一路</font>”的新走廊建设</a></h4>
                                            <p>“一带一路”的构想具有开放性和包容性。本文主要论证葡语国家形成了一条独特的经济文化走廊。从地理分布的特点来看，这一历史原因形成的经济文化走廊有别于传统意义上的陆路走廊，海洋是连接各个葡语...</p>
                                        </li>
                                        <li>
                                            <!-- <p class="section-col"></p> -->
                                            <h4><a href="/guide/en/elasticsearch/reference/5.3/search-request-sort.html">葡语国家与“<font color="#FF0000">一带一路</font>”的新走廊建设</a></h4>
                                            <p>“一带一路”的构想具有开放性和包容性。本文主要论证葡语国家形成了一条独特的经济文化走廊。从地理分布的特点来看，这一历史原因形成的经济文化走廊有别于传统意义上的陆路走廊，海洋是连接各个葡语...</p>
                                        </li>
                                    </ul>
                                </div>
                                <div id="search-result-pagination" class="light-theme simple-pagination clearfix m-b-60">
                                    加载更多
                                </div>
                            </div>
                            <div class="col-lg-3 col-md-3 col-sm-3 col-xs-12 second-search-wrapper right-db-list">
                                <label>数据库</label>
                                <ul>
                                    <ol>
                                        中国社会发展数据库（2000）
                                    </ol>
                                    <ol>
                                        中国经济发展数据库（1861）
                                    </ol>
                                    <ol>
                                        中国行业发展数据库（3329）
                                    </ol>
                                </ul>
                            </div>
                            <div class="col-lg-3 col-md-3 col-sm-3 col-xs-12 second-search-wrapper">
                                <label>结果中检索</label>
                                <div class="form-group">
                                    <input type="text" class="form-control" id="secTitle" placeholder="标题">
                                </div>
                                <div class="form-group">
                                    <input type="text" class="form-control" id="secAuthor" placeholder="作者">
                                </div>
                                <div class="form-group">
                                    <input type="text" class="form-control" id="secPublishDateBegin" placeholder="出版日期开始年月yyyy-mm">
                                </div>
                                <div class="form-group">
                                    <input type="text" class="form-control" id="secPublishDateEnd" placeholder="出版日期结束年月yyyy-mm">
                                </div>
                                <button type="submit" class="btn btn-default pull-right second-search-btn">&nbsp;确&nbsp;定&nbsp;</button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</div>
</div>
</template>

<script>
export default {
    name: 'app',
    data() {
        return {
            searchKey: '',
            isCancelShow: false,
            showSuggest: false,
            doChose: false,
            suggests: [
                'search_analyzer1', 'search_analyzer2', 'search_analyzer3', 'search_analyzer4', 'search_analyzer5'
            ],
            classifies: [
                '哲学、宗教(256)', '社会科学总论(311)', '政治、法律(200)', '军事(20)', '经济(831)'
            ],
            total: 231
        }
    },
    methods: {
        choseSuggest(event) {
            this.doChose = true;
            this.searchKey = $(event.currentTarget).text();
            this.showSuggest = false;
        },
        cancelSearchInput() {
            this.searchKey = '';
        }
    },
    watch: {
        searchKey(newVal, oldVal) {
            if (this.doChose) {
                this.doChose = false;
                return;
            }
            // Todo fix suggest list data
            console.log(newVal);
            if (newVal.length > 0) {
                this.isCancelShow = true;
                this.showSuggest = true;
            } else {
                this.isCancelShow = false;
                this.showSuggest = false;
            }
        }
    }
}
</script>

<style scoped>
html,
body {
    -webkit-font-smoothing: antialiased;
    overflow-x: hidden;
    background: #fff;
    color: #444;
    line-height: 26px;
    font-family: "Open Sans", "arial, helvetica, sans-serif";
    font-size: 16px;
    font-weight: 400;
}

.searchbox-wrapper {
    background: #00a9e5;
}

.search-result-wrapper {
    padding: 40px 0;
}

.search-result-wrapper .big-search {
    position: relative;
    width: 97%;
}

.big-search i.big-search-icon {
    background: transparent url(./assets/search.svg) no-repeat scroll left 0/80% auto;
    bottom: 0;
    height: 32px;
    right: 0;
    margin: auto;
    position: absolute;
    top: 0;
    width: 32px;
}

.big-search i.cancel-icon {
    background: transparent url(./assets/cancel.svg) no-repeat scroll left 0/80% auto;
    bottom: 0;
    height: 28px;
    right: 35px;
    margin: auto;
    position: absolute;
    top: 0;
    width: 28px;
    cursor: pointer;
}

i,
em {
    font-style: italic;
}

.search-result-wrapper .big-search #searchfrm {
    text-align: left;
    width: 100% !important;
}

.tags-wrapper,
.search-tags-wrapper {
    border-bottom: 1px solid #fff;
    cursor: text;
    display: inline-block;
    margin: 0;
    padding: 0 0 5px 5px;
    vertical-align: middle;
    width: 100%;
}

ul,
ul li {
    background: none;
    list-style-type: none;
    margin: 0;
    padding: 0;
}

ul,
ol {
    margin-top: 0;
    margin-bottom: 10px;
}

.tags-wrapper li:only-of-type,
.search-tags-wrapper li:only-of-type {
    width: 100%;
}

.tags-wrapper li:only-of-type,
.search-tags-wrapper li:only-of-type {
    width: 100%;
}

.search-tags-wrapper li {
    border: 0;
    padding: 0;
}

.tags-wrapper li,
.search-tags-wrapper li {
    display: inline-block;
    margin: 0;
    vertical-align: middle;
}

.tags-wrapper li,
.search-tags-wrapper li {
    display: inline-block;
    margin: 0;
    vertical-align: middle;
}

ul,
ul li {
    background: none;
    list-style-type: none;
    margin: 0;
    padding: 0;
}

.search-result-wrapper .big-search #searchfrm .global-input {
    background: transparent;
    box-shadow: none;
}

.search-result-wrapper .big-search input {
    border: 0;
    padding: 0;
}

.big-search input,
.big-search input[type=text],
.big-search input[type=email] {
    background-color: transparent;
    border: medium none;
    box-sizing: border-box;
    box-shadow: none;
    color: #fff;
    display: inline-block;
    font-size: 1.5em;
    font-weight: 500;
    letter-spacing: 0.02em;
    line-height: normal;
    margin: 0px;
    outline: medium none;
    vertical-align: middle;
    width: 98%;
}

.big-search input,
.big-search input[type=text],
.big-search input[type=email] {
    background-color: transparent;
    border: medium none;
    box-sizing: border-box;
    box-shadow: none;
    color: #fff;
    display: inline-block;
    font-size: 1.5em;
    font-weight: 500;
    letter-spacing: 0.02em;
    line-height: normal;
    margin: 0px;
    outline: medium none;
    vertical-align: middle;
    width: 98%;
}

.form-control {
    height: 40px;
}

.form-control {
    display: block;
    width: 100%;
    height: 34px;
    padding: 6px 12px;
    font-size: 14px;
    line-height: 1.42857;
    color: #555555;
    background-color: #fff;
    background-image: none;
    border: 1px solid #ccc;
    border-radius: 4px;
    -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
    box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
    -webkit-transition: border-color ease-in-out 0.15s, box-shadow ease-in-out 0.15s;
    -o-transition: border-color ease-in-out 0.15s, box-shadow ease-in-out 0.15s;
    transition: border-color ease-in-out 0.15s, box-shadow ease-in-out 0.15s;
}

.form-control {
    height: 40px;
}

.form-control {
    display: block;
    width: 100%;
    height: 34px;
    padding: 6px 12px;
    font-size: 14px;
    line-height: 1.42857;
    color: #555555;
    background-color: #fff;
    background-image: none;
    border: 1px solid #ccc;
    border-radius: 4px;
    -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
    box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
    -webkit-transition: border-color ease-in-out 0.15s, box-shadow ease-in-out 0.15s;
    -o-transition: border-color ease-in-out 0.15s, box-shadow ease-in-out 0.15s;
    transition: border-color ease-in-out 0.15s, box-shadow ease-in-out 0.15s;
}

input,
textarea,
select,
p,
span {
    font-size: 16px;
    font-weight: normal;
}

input,
button,
select,
textarea {
    font-family: inherit;
    font-size: inherit;
    line-height: inherit;
}

input {
    line-height: normal;
}

button,
input,
optgroup,
select,
textarea {
    color: inherit;
    font: inherit;
    margin: 0;
}

input,
textarea,
select,
p,
span {
    font-size: 16px;
    font-weight: normal;
}

input,
button,
select,
textarea {
    font-family: inherit;
    font-size: inherit;
    line-height: inherit;
}

input {
    line-height: normal;
}

button,
input,
optgroup,
select,
textarea {
    color: inherit;
    font: inherit;
    margin: 0;
}

* {
    -webkit-box-sizing: border-box;
    -moz-box-sizing: border-box;
    box-sizing: border-box;
}

input {
    -webkit-appearance: textfield;
    background-color: white;
    -webkit-rtl-ordering: logical;
    user-select: text;
    cursor: auto;
    padding: 1px;
    border-width: 2px;
    border-style: inset;
    border-color: initial;
    border-image: initial;
}

input,
textarea,
select,
button {
    text-rendering: auto;
    color: initial;
    letter-spacing: normal;
    word-spacing: normal;
    text-transform: none;
    text-indent: 0px;
    text-shadow: none;
    display: inline-block;
    text-align: start;
    margin: 0em 0em 0em 0em;
    font: 11px system-ui;
}

input,
textarea,
select,
button,
meter,
progress {
    -webkit-writing-mode: horizontal-tb;
}

.search-btn {
    cursor: pointer;
}

.search-result-wrapper .autocomplete-suggestions {
    z-index: 1 !important;
}

.autocomplete-suggestions {
    border-top: 1px solid #CCCCCC;
    border-right: 1px solid #CCCCCC;
    border-bottom: 1px solid #CCCCCC;
    border-left: 1px solid #CCCCCC;
    border-bottom-left-radius: 2px;
    border-bottom-right-radius: 2px;
    background: #fff;
    overflow-x: hidden;
    padding: 2% 1%;
    margin-top: -1px;
    height: auto;
    left: 10px !important;
    width: 95% !important;
}

.autocomplete-suggestions .autocomplete-suggestion {
    border: 0;
    padding: 5px 2%;
    list-style: none;
    white-space: pre-wrap;
    overflow: hidden;
    cursor: pointer;
}

.autocomplete-suggestion:hover {
    background-color: #00a9e5;
    color: #fff;
}

.m-t-40 {
    margin-top: 40px;
}

.bdr-btm {
    border-bottom: 1px solid #CCCCCC;
}

.m-b-30 {
    margin-bottom: 30px;
}

.pull-right {
    float: right !important;
}

.search-count {
    color: #999;
    font-size: 14px;
    margin: 0;
    text-align: right;
}

p {
    font-size: 16px;
    font-weight: normal;
}

.sorting-tab-content {
    display: block;
}

.section-col,
.sorting-tab-content {
    display: inline-block;
    margin-right: 10px;
    margin-bottom: 0;
}

.tab h4 {
    margin-bottom: 5px;
}

.section-col,
h4 {
    display: inline-block;
}

h4,
.paragraph‐title {
    line-height: 42px;
    font-size: 30px;
    font-weight: 300;
}

h1,
h2,
h3,
h4,
h5,
h6,
.h1,
.h2,
.h3,
.h4,
.h5,
.h6 {
    margin: 0px;
    font-family: "Open Sans";
    font-weight: 400;
    color: #000;
}

h4>a {
    margin: 0px;
    font-family: "Open Sans";
    font-weight: 400;
    color: #000;
}

.simple-pagination {
    padding: 10px;
    background: #ddd;
    text-align: center;
    color: #666;
    cursor: pointer;
    margin: 40px 0;
}

.sidebar-content-wrapper,
.rtp-sidebar-content-wrapper {
    float: left;
    border-bottom: 1px solid #CCCCCC;
    padding: 38px 0;
    clear: both;
    width: 100%;
}

.second-search-wrapper {
    padding: 5px;
    background-color: #eee;
}

.second-search-wrapper label {
    margin: 5px 5px 5px -8px;
    background-color: #00a9e5;
    padding: 5px 10px;
    color: #fff;
    font-size: 16px;
}

.second-search-wrapper div {
    margin-bottom: 10px;
}

.right-db-list {
    margin-bottom: 20px;
}

.right-db-list ul ol {
    padding-left: 20px;
}

.nav-tabs>li.active>a,
.nav-tabs>li.active>a:focus,
.nav-tabs>li.active>a:hover {
    border: none;
}

.classify-list .tab-pane {
    margin: 15px;
}

.classify-list ul {
    display: inline;
    margin: 0 15px;
}

.classify-tab li a {
    font-size: 16px;
}

.classify-list ol {
    display: inline;
    padding-left: 0;
    padding-right: 15px;
    cursor: pointer;
}

.classify-list {
    border-bottom: 1px solid #ccc;
}

.result-list ul li {
    margin-bottom: 40px
}

.second-search-btn {
    border-radius: 0px;
}
</style>
