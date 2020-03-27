<style scoped>
/* .swiper-container {
    width: 100%;
    height: 100%;
} */

.demo-swiper2 .swiper-slide {
    background: transparent;
    width: 40%;
    display: -webkit-box;
    display: -ms-flexbox;
    display: -webkit-flex;
    display: flex;
    -webkit-box-pack: center;
    -ms-flex-pack: center;
    -webkit-justify-content: center;
    justify-content: center;
    -webkit-box-align: center;
    -ms-flex-align: center;
    -webkit-align-items: center;
    align-items: center;
}
.demo-swiper3 .swiper-slide {
    background: #fff;
    width: 90%;
    display: -webkit-box;
    display: -ms-flexbox;
    display: -webkit-flex;
    display: flex;
    -webkit-box-pack: center;
    -ms-flex-pack: center;
    -webkit-justify-content: center;
    justify-content: center;
    -webkit-box-align: center;
    -ms-flex-align: center;
    -webkit-align-items: center;
    align-items: center;
}
</style>
<template>
<f7-page :page-content="false" @page:init="onPageInit" style="padding-bottom: 50px; background: #001f3e" @page:beforeremove="onPageBeforeRemove">
    <f7-sheet class="demo-sheet-swipe-to-close bg-color-white" :opened="sheetOpened" @sheet:closed="sheetOpened = false" style="height:auto; background-color: transparent;" swipe-to-close backdrop>
        <div class="block no-margin text-align-right">
            <f7-link sheet-close>Đóng</f7-link>
        </div>
        <f7-page-content>
            <f7-toolbar class="no-shadow style-switching" style="height: 150px;" tabbar labels :position="isBottom ? 'bottom' : 'top'">
                <f7-link class="justify-content-center text-color-black" tab-link @click="sheetOpened = false" href="/">
                    <div style="background-color: #ccc; border-radius: 50%; width: 50px; height: 50px; margin-bottom: 10px"></div>
                    <span class="tabbar-label textformat fs-roboto-medium fs-12 text-align-center">Chương trình <br/> khách hàng</span>
                </f7-link>
                <f7-link class="justify-content-center text-color-black" tab-link @click="sheetOpened = false" href="/hop-dong-bao-hiem/">
                    <div style="background-color: #ccc; border-radius: 50%; width: 50px; height: 50px; margin-bottom: 10px"></div>
                    <span class="tabbar-label textformat fs-roboto-medium fs-12 text-align-center">Hợp đồng <br/> bảo hiểm</span>
                </f7-link>
            </f7-toolbar>
        </f7-page-content>
    </f7-sheet>
    <f7-toolbar class="no-shadow md" style="height: 80px; background-color: transparent;" tabbar labels :position="isBottom ? 'bottom' : 'top'">
        <f7-link style="height: 50px; top: 15px; background-color: #00427a" class="justify-content-center" @click="showNavGame= true" tab-link-active tab-link="#tab-home">
            <!-- <i class="fa fa-home icon" style="font-size: 20px" aria-hidden="true"></i> -->
            <img src="./../img/icon-home.png" alt="">
            <span class="tabbar-label textformat fs-OpenSans-Regular fs-12">Trang chủ</span>
        </f7-link>
        <f7-link style="height: 50px; top: 15px; background-color: #00427a" class="justify-content-center" @click="showNavGame= false" tab-link="#tab-voucher1">
            <img src="./../img/icon-uu-dai.png" alt="">
            <span class="tabbar-label textformat fs-OpenSans-Regular fs-12">Ưu đãi</span>
        </f7-link>
        <f7-link style="top: 6px;" class="justify-content-center style-after" tab-link @click="sheetOpened = false">
            <span style="font-size: 20px; top: -10px; position: relative; border-radius: 50%; width: 50px; height: 50px;  background: -webkit-gradient(linear, left top, right top, from(#0072ff), to(#00d4ff));
    background: linear-gradient(90deg, #0072ff 0%, #00d4ff 100%);display: block;line-height: 50px;text-align: center;color: #fff;">
                <img src="./../img/icon-kham-pha.png" alt="">
            </span>
            <span class="tabbar-label textformat fs-OpenSans-Regular fs-12" style="margin-top: -7px;">Khám phá</span>
        </f7-link>
        <f7-link style="height: 50px; top: 15px; background-color: #00427a" class="justify-content-center" @click="showNavGame= false" tab-link="#tab-bh-online1">
            <!-- <i class="fa fa-address-card icon" style="font-size: 20px" aria-hidden="true"></i> -->
            <img src="./../img/icon-bh-online.png" alt="">
            <span class="tabbar-label textformat fs-OpenSans-Regular fs-12">BH Online</span>
        </f7-link>
        <f7-link style="height: 50px; top: 15px; background-color: #00427a" class="justify-content-center" @click="showNavGame= false" tab-link="#tab-ca-nhan1">
            <!-- <i class="fa fa-user icon" style="font-size: 20px" aria-hidden="true"></i> -->
            <img src="./../img/icon-ca-nhan.png" alt="">
            <span class="tabbar-label textformat fs-OpenSans-Regular fs-12">Cá nhân</span>
        </f7-link>
    </f7-toolbar>
    <f7-tabs>
        <f7-tab id="tab-home" class="page-content" tab-active style="padding-top: 0px; padding-bottom: 50px;">
            <div>
                <div>
                    <img style="width: 100%" src="./../img/game-top.png" alt="">
                </div>
                <div class="text-align-center" style="height: 35px; background-color: #001f3e">
                    <f7-link class="text-color-white fs-OpenSans-Regular fs-14" style="height: 35px; line-height: 35px;">Xem tất cả <i class="fa fa-angle-double-right" style="margin-left: 5px" aria-hidden="true"></i></f7-link>
                </div>

            </div>
            <div style="background-color: #003b72; position: relative">
                <div class="block no-margin" style="padding-top: 20px; padding-bottom: 40px">
                    <h3 class="fs-opensans-semibold fs-16 text-color-white no-margin-bottom">Xin chào Nguyễn Minh Tuấn</h3>
                    <p class="fs-OpenSans-Regular fs-14 text-color-white" style="margin-top: 10px">
                        Cho ngày mai tốt hơn, <br/>từ hôm nay
                    </p>
                </div>
                <div style="position: absolute; bottom: 0; right: 15px;">
                    <img src="./../img/icon-hello.png" alt="">
                </div>
            </div>
            <div class="block no-padding" style="margin-top: 15px; margin-bottom: 0px">
                <div class="swiper-container swiper-init demo-swiper demo-swiper3" style="padding-right: 15px; padding-left: 15px;">
                    <div class="swiper-wrapper">
                        <div class="swiper-slide" style="border-radius: 10px; position: relative; overflow: hidden;">
                            <f7-link class="display-block style-after-mask" style="width: 100%; border-radius: 10px; padding: 20px 15px; background: #fff; box-shadow: 0 0 8px rgba(0, 0, 0, 0.05);">
                                <div class="display-flex align-items-center justify-content-space-between" style="margin-bottom: 10px">
                                    <div class="fs-OpenSans-Regular fs-14" style="color: #01427a;">Đóng phí HĐ</div>
                                    <div class="pointvoucher text-color-black fs-OpenSans-Regular fs-12">Thứ hai (20/02)</div>
                                </div>
                                <div class="display-flex align-items-center justify-content-space-between">
                                    <div class="fs-OpenSans-Regular text-color-black fs-12" style="color: #01427a">Bảo hiểm bệnh hiểm nghèo</div>
                                    <div class="pointvoucher text-color-black fs-OpenSans-Bold fs-12">+20 điểm</div>
                                </div>
                            </f7-link>
                        </div>
                        <div class="swiper-slide" style="border-radius: 10px; position: relative; overflow: hidden;">
                            <f7-link class="display-block style-after-mask" style="width: 100%; border-radius: 10px; padding: 20px 15px; background: #fff; box-shadow: 0 0 8px rgba(0, 0, 0, 0.05);">
                                <div class="display-flex align-items-center justify-content-space-between" style="margin-bottom: 10px">
                                    <div class="fs-OpenSans-Regular fs-14" style="color: #01427a;">Đóng phí HĐ</div>
                                    <div class="pointvoucher text-color-black fs-OpenSans-Regular fs-12">Thứ hai (20/02)</div>
                                </div>
                                <div class="display-flex align-items-center justify-content-space-between">
                                    <div class="fs-OpenSans-Regular text-color-black fs-12" style="color: #01427a">Bảo hiểm bệnh hiểm nghèo</div>
                                    <div class="pointvoucher text-color-black fs-OpenSans-Bold fs-12">+20 điểm</div>
                                </div>
                            </f7-link>
                        </div>
                    </div>
                    <div class="swiper-pagination"></div>
                </div>
            </div>
            <!-- <div class="block no-margin-bottom" style="margin-top: 15px">
                <div style="border-radius: 10px; position: relative; overflow: hidden;">
                    <f7-link class="display-block style-after-mask-info" style="width: 100%; border-radius: 10px; padding: 20px 15px; background: #fff; box-shadow: 0 0 8px rgba(0, 0, 0, 0.05);">
                        <div class="display-flex align-items-center justify-content-space-between" style="margin-bottom: 10px">
                            <div class="fs-OpenSans-Regular fs-14" style="color: #01427a;">Chơi game</div>
                            <div class="pointvoucher text-color-black fs-OpenSans-Regular fs-12">Thứ hai (20/02)</div>
                        </div>
                        <div class="display-flex align-items-center justify-content-space-between">
                            <div class="fs-OpenSans-Regular text-color-black fs-12" style="color: #01427a">Lắc heo vàng</div>
                            <div class="pointvoucher text-color-black fs-OpenSans-Bold fs-12">+20 điểm</div>
                        </div>
                    </f7-link>
                </div>
                
            </div> -->
            <div class="block no-margin-bottom no-padding" style="margin-top: 15px">
                <div class="list no-margin no-hairlines">
                    <ul style="background: transparent;">
                        <li>
                            <a href="#" class="item-link item-content no-chevron">
                                <div class="item-inner">
                                    <div class="item-title fs-OpenSans-Regular fs-16 text-color-white">Thông báo</div>
                                    <div class="item-after fs-OpenSans-Regular fs-14 align-items-center" style="color: #f7941e">Xem chi tiết <i class="fa fa-angle-double-right" style="margin-left: 5px" aria-hidden="true"></i></div>
                                </div>
                            </a>
                        </li>
                    </ul>
                </div>
                <div class="block no-margin no-padding">
                    <div class="swiper-container swiper-init demo-swiper demo-swiper3" style="padding-right: 15px; padding-left: 15px;">
                        <div class="swiper-wrapper">
                            <div class="swiper-slide" style="border-radius: 10px; position: relative; overflow: hidden;">
                                <f7-link class="display-block" style="width: 100%; border-radius: 10px;">
                                    <img style="width: 100%" src="./../img/img-thong-bao.png" alt="">
                                </f7-link>
                            </div>
                            <div class="swiper-slide" style="border-radius: 10px; position: relative; overflow: hidden;">
                                <f7-link class="display-block style-after-mask" style="width: 100%; border-radius: 10px;">
                                    <img style="width: 100%" src="./../img/img-thong-bao.png" alt="">
                                </f7-link>
                            </div>
                        </div>
                        <div class="swiper-pagination"></div>
                    </div>
                </div>
            </div>
            <div class="block no-margin-bottom no-padding" style="margin-top: 15px">
                <div class="list no-margin no-hairlines">
                    <ul style="background: transparent;">
                        <li>
                            <a href="#" class="item-link item-content no-chevron">
                                <div class="item-inner">
                                    <div class="item-title fs-OpenSans-Regular fs-16 text-color-white">Khuyến mãi</div>
                                    <div class="item-after fs-OpenSans-Regular fs-14 align-items-center" style="color: #f7941e">Private Promotion (2)</div>
                                </div>
                            </a>
                        </li>
                    </ul>
                </div>
                <div class="block no-margin no-padding">
                    <div class="swiper-container swiper-init demo-swiper demo-swiper3" style="padding-right: 15px; padding-left: 15px;">
                        <div class="swiper-wrapper">
                            <div class="swiper-slide" style="border-radius: 10px; position: relative; overflow: hidden;">
                                <f7-link class="display-block" style="width: 100%; border-radius: 10px;">
                                    <img style="width: 100%" src="./../img/img-khuyen-mai.png" alt="">
                                </f7-link>
                            </div>
                            <div class="swiper-slide" style="border-radius: 10px; position: relative; overflow: hidden;">
                                <f7-link class="display-block style-after-mask" style="width: 100%; border-radius: 10px;">
                                    <img style="width: 100%" src="./../img/img-khuyen-mai.png" alt="">
                                </f7-link>
                            </div>
                        </div>
                        <div class="swiper-pagination"></div>
                    </div>
                </div>
            </div>
            <div class="block no-margin-bottom no-padding" style="margin-top: 15px">
                <div class="list no-margin no-hairlines">
                    <ul style="background: transparent;">
                        <li>
                            <a href="#" class="item-link item-content no-chevron">
                                <div class="item-inner">
                                    <div class="item-title fs-OpenSans-Regular fs-16 text-color-white">Đối tác</div>
                                    <div class="item-after fs-OpenSans-Regular fs-14 align-items-center" style="color: #f7941e">Xem chi tiết <i class="fa fa-angle-double-right" style="margin-left: 5px" aria-hidden="true"></i></div>
                                </div>
                            </a>
                        </li>
                    </ul>
                </div>
                <div class="block no-margin no-padding">
                    <div class="swiper-container swiper-init demo-swiper demo-swiper2" style="padding-right: 15px; padding-left: 15px;">
                        <div class="swiper-wrapper">
                            <div class="swiper-slide" style="border-radius: 10px; position: relative; overflow: hidden;">
                                <f7-link class="display-block" style="width: 100%; border-radius: 10px;">
                                    <img style="width: 100%" src="./../img/img-doi-tac-1.png" alt="">
                                    <div>
                                        <p class="fs-OpenSans-Regular fs-14 text-color-white" style="margin-top: 10px; margin-bottom: 0px;">
                                            Highlands Coffee <br/>Ưu đãi tháng 3
                                        </p>
                                    </div>
                                </f7-link>
                            </div>
                            <div class="swiper-slide" style="border-radius: 10px; position: relative; overflow: hidden;">
                                <f7-link class="display-block" style="width: 100%; border-radius: 10px;">
                                    <img style="width: 100%" src="./../img/img-doi-tac-2.png" alt="">
                                    <div>
                                        <p class="fs-OpenSans-Regular fs-14 text-color-white" style="margin-top: 10px; margin-bottom: 0px;">
                                            Hội Việt Mỹ VUS <br/>Anh văn giao tiếp
                                        </p>
                                    </div>
                                </f7-link>
                            </div>
                            <div class="swiper-slide" style="border-radius: 10px; position: relative; overflow: hidden;">
                                <f7-link class="display-block" style="width: 100%; border-radius: 10px;">
                                    <img style="width: 100%" src="./../img/img-doi-tac-1.png" alt="">
                                    <div>
                                        <p class="fs-OpenSans-Regular fs-14 text-color-white" style="margin-top: 10px; margin-bottom: 0px;">
                                            Highlands Coffee <br/>Ưu đãi tháng 3
                                        </p>
                                    </div>
                                </f7-link>
                            </div>
                        </div>
                        <div class="swiper-pagination"></div>
                    </div>
                </div>
            </div>
            <div class="block no-margin-bottom no-padding" style="margin-top: 15px">
                <div class="list no-margin no-hairlines">
                    <ul style="background: transparent;">
                        <li>
                            <a href="#" class="item-link item-content no-chevron">
                                <div class="item-inner">
                                    <div class="item-title fs-OpenSans-Regular fs-16 text-color-white">Bài viết</div>
                                    <div class="item-after fs-OpenSans-Regular fs-14 align-items-center" style="color: #f7941e">Xem chi tiết <i class="fa fa-angle-double-right" style="margin-left: 5px" aria-hidden="true"></i></div>
                                </div>
                            </a>
                        </li>
                    </ul>
                </div>
                <div class="block no-margin no-padding">
                    <div class="swiper-container swiper-init demo-swiper demo-swiper2" style="padding-right: 15px; padding-left: 15px;">
                        <div class="swiper-wrapper">
                            <div class="swiper-slide" style="border-radius: 10px; position: relative; overflow: hidden;">
                                <f7-link class="display-block" style="width: 100%; border-radius: 10px;">
                                    <img style="width: 100%" src="./../img/img-bai-viet-1.png" alt="">
                                </f7-link>
                            </div>
                            <div class="swiper-slide" style="border-radius: 10px; position: relative; overflow: hidden;">
                                <f7-link class="display-block" style="width: 100%; border-radius: 10px;">
                                    <img style="width: 100%" src="./../img/img-bai-viet-2.png" alt="">
                                </f7-link>
                            </div>
                            <div class="swiper-slide" style="border-radius: 10px; position: relative; overflow: hidden;">
                                <f7-link class="display-block" style="width: 100%; border-radius: 10px;">
                                    <img style="width: 100%" src="./../img/img-bai-viet-1.png" alt="">
                                </f7-link>
                            </div>
                        </div>
                        <div class="swiper-pagination"></div>
                    </div>
                </div>
            </div>
        </f7-tab>
        <f7-tab id="tab-voucher" class="page-content" style="padding-top: 0px; padding-bottom: 50px;">
            <!-- <div class="list media-list no-margin">
                <ul>
                    <li>
                        <a href="#" class="item-link item-content">
                            <div class="item-media align-self-center"><i class="fa fa-user fa-2x" aria-hidden="true"></i></div>
                            <div class="item-inner">
                                <div class="item-title fs-roboto-medium fs-15">Nguyễn Văn A</div>
                                <div class="item-title-row">
                                    <div class=" fs-roboto-light fs-13">Thành viên bạc</div>
                                    <div class="item-after fs-roboto-light fs-13">358 điểm</div>
                                </div>
                                <div class="item-subtitle">
                                    <f7-progressbar color="blue" :progress="50"></f7-progressbar>
                                    <div class="item-subtitle fs-roboto-light fs-13" style="padding-top:5px">Thêm 1142 điểm lên thành viên vàng</div>
                                </div>
                            </div>
                        </a>
                    </li>
                </ul>
            </div> -->
            <!-- <div class="style-toolbar">
                <f7-toolbar class="no-shadow no-border" tabbar labels :position="isBottom ? 'bottom' : 'top'">
                    <p class="segmented segmented-strong block ios" style="width: 100%;">
                        <f7-link class="tab-link button fs-roboto-medium fs-15" tab-link-active href="#tab1" style="text-transform: none;">352 điểm</f7-link>
                        <f7-link class="tab-link button fs-roboto-medium fs-15" href="#tab2" style="text-transform: none;">Ví Voucher</f7-link>
                    </p>
                </f7-toolbar>
            </div> -->
            <div class="block no-margin" style="padding-top: 15px; padding-bottom: 15px; background-color: #003f7e;">
                <p class="segmented segmented-raised">
                    <button class="button fs-15 fs-roboto-medium bg-color-white" style="text-transform: capitalize;">51 điểm</button>
                    <button class="button fs-15 fs-roboto-medium bg-color-white" style="text-transform: capitalize;">Ví Voucher</button>

                </p>
            </div>
            <div class="block no-margin no-padding">
                <div class="list no-margin no-hairlines">
                    <ul>
                        <li>
                            <a href="#" class="item-link item-content">
                                <div class="item-inner">
                                    <div class="item-title fs-OpenSans-Bold fs-15">Quà Map Life</div>
                                    <div class="item-after fs-OpenSans-Regular">Xem tất cả</div>
                                </div>
                            </a>
                        </li>
                    </ul>
                </div>
                <div class="block no-margin-bottom" style="margin-top: 10px">
                    <div class="swiper-container swiper-init demo-swiper demo-swiper2">
                        <div class="swiper-wrapper">
                            <div class="swiper-slide">
                                <f7-link class="display-block" style="width: 100%; height: 33vw; border-radius: 5px; background: #ccc; box-shadow: 0 0 8px rgba(0, 0, 0, 0.05);">

                                </f7-link>
                            </div>
                            <div class="swiper-slide">
                                <f7-link class="display-block" style="width: 100%; height: 33vw; border-radius: 5px; background: #ccc; box-shadow: 0 0 8px rgba(0, 0, 0, 0.05);">

                                </f7-link>
                            </div>
                            <div class="swiper-slide">
                                <f7-link class="display-block" style="width: 100%; height: 33vw; border-radius: 5px; background: #ccc; box-shadow: 0 0 8px rgba(0, 0, 0, 0.05);">

                                </f7-link>
                            </div>
                        </div>
                        <div class="swiper-pagination"></div>
                    </div>
                </div>
            </div>
            <div class="block no-margin no-padding">
                <div class="list no-margin no-hairlines">
                    <ul>
                        <li>
                            <a href="#" class="item-link item-content no-chevron">
                                <div class="item-inner">
                                    <div class="fs-OpenSans-Bold fs-15">Danh mục ưu đãi</div>
                                    <!-- <div class="item-after fs-OpenSans-Regular">Xem tất cả</div> -->
                                </div>
                            </a>
                        </li>
                    </ul>
                </div>
                <div class="block no-margin no-padding">
                    <f7-toolbar tabbar scrollable class="no-shadow tabbar-scrollable md" style="height: 60px; background-color: transparent;">
                        <f7-link class="justify-content-center bg-color-white" tab-link-active tab-link="#tab-tat-ca">
                            <i class="fa fa-circle icon" style="font-size: 24px" aria-hidden="true"></i>
                            <span class="tabbar-label textformat fs-roboto-medium fs-12" style="padding-top: 5px; text-transform: initial;">Tất cả</span>
                        </f7-link>
                        <f7-link class="justify-content-center bg-color-white">
                            <i class="fa fa-circle icon" style="font-size: 24px" aria-hidden="true"></i>
                            <span class="tabbar-label textformat fs-roboto-medium fs-12" style="padding-top: 5px; text-transform: initial;">Sức khỏe</span>
                        </f7-link>
                        <f7-link class="justify-content-center bg-color-white">
                            <i class="fa fa-circle icon" style="font-size: 24px" aria-hidden="true"></i>
                            <span class="tabbar-label textformat fs-roboto-medium fs-12" style="padding-top: 5px; text-transform: initial;">Du lịch</span>
                        </f7-link>
                        <f7-link class="justify-content-center bg-color-white">
                            <i class="fa fa-circle icon" style="font-size: 24px" aria-hidden="true"></i>
                            <span class="tabbar-label textformat fs-roboto-medium fs-12" style="padding-top: 5px; text-transform: initial;">Giáo dục</span>
                        </f7-link>
                        <f7-link class="justify-content-center bg-color-white">
                            <i class="fa fa-circle icon" style="font-size: 24px" aria-hidden="true"></i>
                            <span class="tabbar-label textformat fs-roboto-medium fs-12" style="padding-top: 5px; text-transform: initial;">Giải trí (F&B, etc.)</span>
                        </f7-link>
                    </f7-toolbar>
                </div>
            </div>
            <f7-tabs>
                <f7-tab id="tab-tat-ca" tab-active class="page-content" style="padding-top: 0px; padding-bottom: 0px">
                    <!-- <f7-block class="no-padding no-margin">
                        <div class="list media-list no-margin-top" style="margin-bottom: 10px">
                            <ul>
                                <li>
                                    <a href="/chi-tiet-voucher/" class="item-link item-content style-af-bf">
                                        <div class="item-media align-self-center"><img style="border-radius: 5px" src="https://via.placeholder.com/150/000000/FFFFFF/?text=IPaddress.net" width="80" /></div>
                                        <div class="item-inner">
                                            <div style="border-left: 1px dashed var(--f7-messagebar-attachments-border-color); height: 90px; position: absolute; top: 0; bottom: 0; margin: auto auto; left: -8px;"></div>
                                            <div class="item-text fs-roboto-bold text-color-black">Karcher - giảm 200.000đ cho hóa đơn từ 1.500.000đ</div>
                                            <div class="item-text fs-roboto-light fs-13">HSD: 01/03/2020</div>
                                            <div class="item-text fs-roboto-light fs-15 text-color-orange text-align-right">Dùng ngay</div>
                                        </div>
                                    </a>
                                </li>
                            </ul>
                        </div>
                        <div class="list media-list no-margin-top" style="margin-bottom: 10px">
                            <ul>
                                <li>
                                    <a href="/chi-tiet-voucher/" class="item-link item-content style-af-bf">
                                        <div class="item-media align-self-center"><img style="border-radius: 5px" src="https://via.placeholder.com/150/000000/FFFFFF/?text=IPaddress.net" width="80" /></div>
                                        <div class="item-inner">
                                            <div style="border-left: 1px dashed var(--f7-messagebar-attachments-border-color); height: 90px; position: absolute; top: 0; bottom: 0; margin: auto auto; left: -8px;"></div>
                                            <div class="item-text fs-roboto-bold text-color-black">Karcher - giảm 200.000đ cho hóa đơn từ 1.500.000đ</div>
                                            <div class="item-text fs-roboto-light fs-13">HSD: 01/03/2020</div>
                                            <div class="item-text fs-roboto-light fs-15 text-color-orange text-align-right">Dùng ngay</div>
                                        </div>
                                    </a>
                                </li>
                            </ul>
                        </div>
                        <div class="list media-list no-margin-top" style="margin-bottom: 10px">
                            <ul>
                                <li>
                                    <a href="/chi-tiet-voucher/" class="item-link item-content style-af-bf">
                                        <div class="item-media align-self-center"><img style="border-radius: 5px" src="https://via.placeholder.com/150/000000/FFFFFF/?text=IPaddress.net" width="80" /></div>
                                        <div class="item-inner">
                                            <div style="border-left: 1px dashed var(--f7-messagebar-attachments-border-color); height: 90px; position: absolute; top: 0; bottom: 0; margin: auto auto; left: -8px;"></div>
                                            <div class="item-text fs-roboto-bold text-color-black">Karcher - giảm 200.000đ cho hóa đơn từ 1.500.000đ</div>
                                            <div class="item-text fs-roboto-light fs-13">HSD: 01/03/2020</div>
                                            <div class="item-text fs-roboto-light fs-15 text-color-orange text-align-right">Dùng ngay</div>
                                        </div>
                                    </a>
                                </li>
                            </ul>
                        </div>
                    </f7-block> -->
                    <div class="block no-margin no-padding">
                        <div class="list no-margin">
                            <ul>
                                <li>
                                    <a href="#" class="item-link item-content">
                                        <div class="item-inner">
                                            <div class="fs-OpenSans-Bold fs-15">Sức khỏe</div>
                                            <div class="item-after fs-OpenSans-Regular">Xem tất cả</div>
                                        </div>
                                    </a>
                                </li>
                            </ul>
                        </div>
                        <div class="block no-margin-bottom" style="margin-top: 10px">
                            <div class="swiper-container swiper-init demo-swiper demo-swiper2">
                                <div class="swiper-wrapper">
                                    <div class="swiper-slide">
                                        <f7-link class="display-block" style="width: 100%; height: 33vw; border-radius: 5px; background: #ccc; box-shadow: 0 0 8px rgba(0, 0, 0, 0.05);">

                                        </f7-link>
                                    </div>
                                    <div class="swiper-slide">
                                        <f7-link class="display-block" style="width: 100%; height: 33vw; border-radius: 5px; background: #ccc; box-shadow: 0 0 8px rgba(0, 0, 0, 0.05);">

                                        </f7-link>
                                    </div>
                                    <div class="swiper-slide">
                                        <f7-link class="display-block" style="width: 100%; height: 33vw; border-radius: 5px; background: #ccc; box-shadow: 0 0 8px rgba(0, 0, 0, 0.05);">

                                        </f7-link>
                                    </div>
                                </div>
                                <div class="swiper-pagination"></div>
                            </div>
                        </div>
                    </div>
                    <div class="block no-margin no-padding">
                        <div class="list no-margin">
                            <ul>
                                <li>
                                    <a href="#" class="item-link item-content">
                                        <div class="item-inner">
                                            <div class="fs-OpenSans-Bold fs-15">Du lịch</div>
                                            <div class="item-after fs-OpenSans-Regular">Xem tất cả</div>
                                        </div>
                                    </a>
                                </li>
                            </ul>
                        </div>
                        <div class="block no-margin-bottom" style="margin-top: 10px">
                            <div class="swiper-container swiper-init demo-swiper demo-swiper2">
                                <div class="swiper-wrapper">
                                    <div class="swiper-slide">
                                        <f7-link class="display-block" style="width: 100%; height: 33vw; border-radius: 5px; background: #ccc; box-shadow: 0 0 8px rgba(0, 0, 0, 0.05);">

                                        </f7-link>
                                    </div>
                                    <div class="swiper-slide">
                                        <f7-link class="display-block" style="width: 100%; height: 33vw; border-radius: 5px; background: #ccc; box-shadow: 0 0 8px rgba(0, 0, 0, 0.05);">

                                        </f7-link>
                                    </div>
                                    <div class="swiper-slide">
                                        <f7-link class="display-block" style="width: 100%; height: 33vw; border-radius: 5px; background: #ccc; box-shadow: 0 0 8px rgba(0, 0, 0, 0.05);">

                                        </f7-link>
                                    </div>
                                </div>
                                <div class="swiper-pagination"></div>
                            </div>
                        </div>
                    </div>
                </f7-tab>
                <!-- <f7-tab id="tab-suc-khoe" class="page-content" style="padding-top: 0px">
                    <f7-block style="margin: 10px 0px; padding: 0px 10px">
                        <div class="list media-list no-hairlines no-margin">
                            <ul style="margin-bottom: 5px; border-radius: 5px; box-shadow: 0 0 1rem 0 rgba(136, 152, 170, .15) !important;" class="bg-color-white elevation-demo elevation-hover-2 elevation-pressed-1 elevation-transition">
                                <li>
                                    <a href="/chi-tiet-voucher/" class="item-link item-content no-chevron">
                                        <div class="item-inner">
                                            <div class="item-title-row" style="margin-bottom: 5px">
                                                <div class="item-title">Tên nhãn hàng</div>
                                                <div class="item-after fs-roboto-medium fs-13">17:14</div>
                                            </div>
                                            <div style="margin-bottom: 5px"><img class="lazy lazy-fade-in demo-lazy" style="width: 100%; border-radius: 5px" data-src="https://via.placeholder.com/350x150/000000/FFFFFF/" /></div>
                                            <div class="item-text fs-roboto-light fs-15 text-color-gray">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla sagittis tellus ut turpis condimentum, ut dignissim lacus tincidunt. Cras dolor metus, ultrices condimentum sodales sit amet, pharetra sodales eros. Phasellus vel felis tellus. Mauris rutrum ligula nec dapibus feugiat. In vel dui laoreet, commodo augue id, pulvinar lacus.</div>
                                        </div>
                                    </a>
                                </li>
                            </ul>
                        </div>
                    </f7-block>
                    <f7-block style="margin: 10px 0px; padding: 0px 10px">
                        <div class="list media-list no-hairlines no-margin">
                            <ul style="margin-bottom: 5px; border-radius: 5px; box-shadow: 0 0 1rem 0 rgba(136, 152, 170, .15) !important;" class="bg-color-white elevation-demo elevation-hover-2 elevation-pressed-1 elevation-transition">
                                <li>
                                    <a href="/chi-tiet-voucher/" class="item-link item-content no-chevron">
                                        <div class="item-inner">
                                            <div class="item-title-row" style="margin-bottom: 5px">
                                                <div class="item-title">Tên nhãn hàng</div>
                                                <div class="item-after fs-roboto-medium fs-13">17:14</div>
                                            </div>
                                            <div style="margin-bottom: 5px"><img class="lazy lazy-fade-in demo-lazy" style="width: 100%; border-radius: 5px" data-src="https://via.placeholder.com/350x150/000000/FFFFFF/" /></div>
                                            <div class="item-text fs-roboto-light fs-15 text-color-gray">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla sagittis tellus ut turpis condimentum, ut dignissim lacus tincidunt. Cras dolor metus, ultrices condimentum sodales sit amet, pharetra sodales eros. Phasellus vel felis tellus. Mauris rutrum ligula nec dapibus feugiat. In vel dui laoreet, commodo augue id, pulvinar lacus.</div>
                                        </div>
                                    </a>
                                </li>
                            </ul>
                        </div>
                    </f7-block>
                </f7-tab> -->
            </f7-tabs>
        </f7-tab>
        <f7-tab id="tab-bh-online" class="page-content" style="padding-top: 0px; padding-bottom: 50px;">
            <div class="swiper-container swiper-init demo-swiper demo-swiper0">
                <div class="swiper-wrapper">
                    <div class="swiper-slide" style="margin-bottom: 5px !important">
                        <f7-link style="width: 100%; height: 180px; background: #ccc;">

                        </f7-link>
                    </div>
                </div>
                <div class="swiper-pagination"></div>
            </div>
            <div class="block no-margin no-padding">
                <div class="list no-margin no-hairlines">
                    <ul>
                        <li>
                            <a href="#" class="item-link item-content no-chevron">
                                <div class="item-inner">
                                    <div class="item-title fs-OpenSans-Bold fs-15">Sản phẩm Bảo Hiểm online</div>
                                    <!-- <div class="item-after fs-OpenSans-Regular">Xem tất cả</div> -->
                                </div>
                            </a>
                        </li>
                    </ul>
                </div>
                <div class="block no-margin-bottom" style="margin-top: 15px">
                    <div style="margin-bottom: 15px">
                        <div class="card demo-card-header-pic no-margin">
                            <div class="card-header" style="width: 100%; height: 180px; background: #ccc;">

                            </div>
                            <div class="card-content card-content-padding">
                                <p class="fs-15" style="margin-bottom: 0px;">Bảo Hiểm Bảo Vệ Bệnh Ung Thư 2020</p>
                                <p class="fs-roboto-light fs-15 no-margin-bottom" style="margin-top: 5px;">Mua một lần bảo vệ sức khỏe 1 năm (dành cho cả trẻ em từ 15 ngày tuổi)</p>
                                <p class="fs-roboto-light fs-15 no-margin-bottom" style="margin-top: 5px;">Phí từ: <strong class="text-color-blue">1.160.000 đồng</strong></p>
                                <p class="fs-roboto-light fs-15 no-margin-bottom" style="margin-top: 5px;">Quyền lợi bảo vệ đến <strong class="text-color-blue">400 triệu đồng</strong></p>
                            </div>
                            <div class="card-footer"><a href="#" class="link"></a><a href="#" class="link" style="font-size: 16px">Mua trực tuyến</a></div>
                        </div>
                    </div>
                    <div style="margin-bottom: 15px">
                        <div class="card demo-card-header-pic no-margin">
                            <div class="card-header" style="width: 100%; height: 180px; background: #ccc;">
                                <div class="discount-item-card__badge-wrapper discount-fs-item-card__badge-wrapper">
                                    <div class="discount-badge discount-badge--fixed-width discount-badge--promotion">
                                        <div class="discount-badge--promotion__label-wrapper discount-badge--promotion__label-wrapper--vi">
                                            <span class="percent fs-15">50%</span>
                                            <span style="font-size: 10px; padding-top: 3px;" class="discount-badge--promotion__label-wrapper__off-label">
                                                31.3
                                            </span>
                                        </div>
                                    </div>
                                </div>
                            </div>
                            <div class="card-content card-content-padding">
                                <p class="fs-15" style="margin-bottom: 0px;">Bảo Hiểm Bảo Vệ Bệnh Hiểm Nghèo 118 bệnh</p>
                                <p class="fs-roboto-light fs-15 no-margin-bottom" style="margin-top: 5px;">Bảo vệ toàn diện trước các rủi ro thương tật hoặc tử vong do tai nạn</p>
                                <p class="fs-roboto-light fs-15 no-margin-bottom" style="margin-top: 5px;">Phí từ: <strong class="text-color-blue">1.000.000 đồng</strong></p>
                                <p class="fs-roboto-light fs-15 no-margin-bottom" style="margin-top: 5px;">Quyền lợi bảo vệ đến <strong class="text-color-blue">1 tỷ đồng</strong></p>
                            </div>
                            <div class="card-footer"><a href="#" class="link"></a><a href="#" class="link" style="font-size: 16px">Mua trực tuyến</a></div>
                        </div>
                    </div>
                    <div style="margin-bottom: 15px">
                        <div class="card demo-card-header-pic no-margin">
                            <div class="card-header" style="width: 100%; height: 180px; background: #ccc;">

                            </div>
                            <div class="card-content card-content-padding">
                                <p class="fs-15" style="margin-bottom: 0px;">Viện phí nằm viện</p>
                                <p class="fs-roboto-light fs-15 no-margin-bottom" style="margin-top: 5px;">Bảo hiểm ung thư từ giai đoạn đầu tiên</p>
                                <p class="fs-roboto-light fs-15 no-margin-bottom" style="margin-top: 5px;">Phí từ: <strong class="text-color-blue">98.000 đồng</strong></p>
                                <p class="fs-roboto-light fs-15 no-margin-bottom" style="margin-top: 5px;">Quyền lợi bảo vệ đến <strong class="text-color-blue">500 triệu đồng</strong></p>
                            </div>
                            <div class="card-footer"><a href="#" class="link"></a><a href="#" class="link" style="font-size: 16px">Mua trực tuyến</a></div>
                        </div>
                    </div>
                </div>

                <!-- <div class="block no-margin-bottom" style="margin-top: 15px">
                    <f7-row>
                        <f7-col width="100" style="margin-bottom: 10px">
                            <div class="list media-list no-hairlines no-margin">
                                <ul style="margin-bottom: 5px; border-radius: 5px;" class="bg-color-white elevation-demo elevation-hover-2 elevation-pressed-1 elevation-transition">
                                    <li>
                                        <a href="/chi-tiet-voucher/" class="item-link item-content no-chevron">
                                            <div class="item-inner">
                                                <div class="text-align-center" style="margin-bottom: 5px"><img class="lazy lazy-fade-in demo-lazy" style="width: 80px; height: 80px; border-radius: 5px; background: #ccc;" data-src="" /></div>
                                                <div class="fs-roboto-light fs-15 text-color-gray text-align-center">Bảo hiểm sức khỏe</div>
                                                <div class="fs-roboto-medium fs-15 text-color-gray text-align-center">VITA - Sống như ý</div>
                                                <div class="fs-roboto-light fs-15 text-color-gray text-align-center">Mua một lần bảo vệ sức khỏe 1 năm (dành cho cả trẻ em từ 15 ngày tuổi)</div>
                                                <div class="fs-roboto-light fs-15 text-align-center">Phí từ: 1.160.000 đồng</div>
                                                <div class="fs-roboto-light fs-15 text-align-center">Quyền lợi bảo vệ đến 400 triệu đồng</div>
                                            </div>
                                        </a>
                                        <div class="block no-margin-bottom" style="margin-top: 20px; padding-bottom: 15px">
                                            <div class="row">
                                                <button class="col button button-fill">Mua trực tuyến</button>
                                            </div>
                                        </div>
                                    </li>
                                </ul>
                            </div>
                        </f7-col>
                        <f7-col width="100" style="margin-bottom: 10px">
                            <div class="list media-list no-hairlines no-margin">
                                <ul style="margin-bottom: 5px; border-radius: 5px;" class="bg-color-white elevation-demo elevation-hover-2 elevation-pressed-1 elevation-transition">
                                    <li>
                                        <a href="/chi-tiet-voucher/" class="item-link item-content no-chevron">
                                            <div class="item-inner">
                                                <div class="text-align-center" style="margin-bottom: 5px"><img class="lazy lazy-fade-in demo-lazy" style="width: 80px; height: 80px; border-radius: 5px; background: #ccc;" data-src="" /></div>
                                                <div class="fs-roboto-light fs-15 text-color-gray text-align-center">Bảo hiểm sức khỏe</div>
                                                <div class="fs-roboto-medium fs-15 text-color-gray text-align-center">VITA - Sống như ý</div>
                                                <div class="fs-roboto-light fs-15 text-color-gray text-align-center">Mua một lần bảo vệ sức khỏe 1 năm (dành cho cả trẻ em từ 15 ngày tuổi)</div>
                                                <div class="fs-roboto-light fs-15 text-align-center">Phí từ: 1.160.000 đồng</div>
                                                <div class="fs-roboto-light fs-15 text-align-center">Quyền lợi bảo vệ đến 400 triệu đồng</div>
                                            </div>
                                        </a>
                                        <div class="block" style="margin-top: 20px; padding-bottom: 15px">
                                            <div class="row">
                                                <button class="col button button-fill">Mua trực tuyến</button>
                                            </div>
                                        </div>
                                    </li>
                                </ul>
                            </div>
                        </f7-col>
                    </f7-row>
                </div> -->
            </div>
        </f7-tab>
        <f7-tab id="tab-ca-nhan" class="page-content" style="padding-top: 0px; padding-bottom: 50px;">
            <div class="block bg-color-white no-margin" style="position: relative; padding-top: 15px; padding-bottom: 15px">
                <img src="./../img/background-connection.jpg" alt="" style="height: 180px; width: 100%; object-fit: cover; border-radius: 10px">
                <div style="position: absolute; top: 30px; width: 100%; right: 30px; text-align: right;"><i class="fa fa-diamond fa-2x text-color-white" aria-hidden="true"></i></div>
                <div class="list media-list no-margin no-hairlines" style="position: absolute; top: 40%; width: 100%;">
                    <ul style="background: transparent;">
                        <li>
                            <f7-link href="" class="item-link item-content">
                                <div class="item-media" style="position: relative">
                                    <img src="./../img/avatar-icon.png" width="80" />
                                    <!-- <i class="fa fa-camera text-color-blue fa-lg" aria-hidden="true" style="position: absolute; bottom: 20px; right: 0;"></i> -->
                                </div>
                                <div class="item-inner align-self-center">
                                    <div class="item-title-row no-chevron">
                                        <div class="item-title fs-roboto-medium fs-15 text-color-white" style="text-transform: uppercase; font-weight: normal;">Nguyễn Văn An</div>
                                        <!-- <div class="item-after fs-OpenSans-Regular text-color-white"><i class="fa fa-pencil fa-lg" aria-hidden="true"></i></div> -->
                                    </div>
                                    <!-- <div class="item-subtitle fs-roboto-light fs-13 text-color-black" style="margin-bottom: 10px">Nhân viên Developer</div> -->
                                    <div class="item-text fs-roboto-light display-block fs-13 text-color-white">
                                        Thành viên Bạc
                                    </div>
                                </div>
                            </f7-link>
                        </li>
                    </ul>
                </div>
            </div>

            <f7-block class="no-margin no-padding">
                <!-- <div class="list media-list no-margin-bottom" style="margin-top: 8px;">
                    <ul>
                        <li>
                            <a href="#" class="item-link item-content">
                                <div class="item-media"><img src="./../img/qrcode.png" width="60" /></div>
                                <div class="item-inner">
                                    <div class="item-title-row">
                                        <div class="fs-OpenSans-Regular fs-15">Nhận ngay gói quà đến 1 triệu khi share QR code giới thiệu</div>
                                    </div>
                                    <div class="item-subtitle fs-roboto-light item-text text-color-orange">Tham gia ngay</div>
                                </div>
                            </a>
                        </li>
                    </ul>
                </div> -->
                <!-- <div class="list accordion-list" style="margin-top: 5px; margin-bottom: 5px">
                    <ul>
                        <li class="accordion-item"><a href="#" class="item-content item-link">
                                <div class="item-inner">
                                    <div class="item-title fs-15">Thông tin cá nhân</div>
                                </div>
                            </a>
                            <div class="accordion-item-content">
                                <div class="list no-margin">
                                    <ul>
                                        <li>
                                            <div class="item-content">
                                                <div class="item-media" style="min-width: 30px"><i class="fa fa-birthday-cake" style="color: #ccc" aria-hidden="true"></i></div>
                                                <div class="item-inner" style="margin-left: 0px">
                                                    <div class="item-title fs-roboto-light fs-15 text-color-black">
                                                        <span style="color: #999">Birthday: 28.05.1991</span>
                                                    </div>
                                                </div>
                                            </div>
                                        </li>
                                        <li>
                                            <div class="item-content">
                                                <div class="item-media" style="min-width: 30px"><i class="fa fa-user" style="font-size: 22px; color: #ccc;" aria-hidden="true"></i></div>
                                                <div class="item-inner" style="margin-left: 0px">
                                                    <div class="item-title fs-roboto-light fs-15 text-color-black"><span style="color: #999">Giới tính: Nam </span></div>
                                                </div>
                                            </div>
                                        </li>
                                        <li>
                                            <div class="item-content">
                                                <div class="item-media" style="min-width: 30px"><i class="fa fa-map-marker" aria-hidden="true" style="font-size: 22px; color: #ccc;"></i></div>
                                                <div class="item-inner" style="margin-left: 0px">
                                                    <div class="fs-roboto-light fs-15 text-color-black"><span style="color: #999; text-transform: capitalize;">Địa chỉ: 74 đường số 2, cư xá đô thành, quận 3. tphcm</span></div>
                                                </div>
                                            </div>
                                        </li>
                                        <li>
                                            <div class="item-content">
                                                <div class="item-media" style="min-width: 30px"><i class="fa fa-phone" aria-hidden="true" style="font-size: 22px; color: #ccc;"></i></div>
                                                <div class="item-inner" style="margin-left: 0px">
                                                    <div class="item-title fs-roboto-light fs-15 text-color-black">
                                                        <span style="color: #999">Điện thoại: 0995833307</span>
                                                    </div>
                                                </div>
                                            </div>
                                        </li>
                                        <li>
                                            <div class="item-content">
                                                <div class="item-media" style="min-width: 30px"><i class="fa fa-envelope" style="font-size: 18px; color: #ccc;" aria-hidden="true"></i></div>
                                                <div class="item-inner" style="margin-left: 0px">
                                                    <div class="item-title fs-roboto-light fs-15 text-color-black"><span style="color: #999">Email: annguyen@gmail.com</span> </div>
                                                </div>
                                            </div>
                                        </li>
                                    </ul>
                                </div>
                            </div>
                        </li>
                    </ul>
                </div> -->
            </f7-block>
            <!-- <div class="block no-margin no-padding">
                <div class="list no-margin">
                    <ul>
                        <li>
                            <a href="#" class="item-link item-content">
                                <div class="item-inner">
                                    <div class="fs-OpenSans-Bold fs-15">...</div>
                                    <div class="item-after fs-OpenSans-Regular">Xem tất cả</div>
                                </div>
                            </a>
                        </li>
                    </ul>
                </div>
                <div class="block no-margin-bottom" style="margin-top: 10px">
                    <div class="swiper-container swiper-init demo-swiper demo-swiper2">
                        <div class="swiper-wrapper">
                            <div class="swiper-slide">
                                <f7-link class="display-block" style="width: 100%; height: 33vw; border-radius: 5px; background: #ccc; box-shadow: 0 0 8px rgba(0, 0, 0, 0.05);">

                                </f7-link>
                            </div>
                            <div class="swiper-slide">
                                <f7-link class="display-block" style="width: 100%; height: 33vw; border-radius: 5px; background: #ccc; box-shadow: 0 0 8px rgba(0, 0, 0, 0.05);">

                                </f7-link>
                            </div>
                            <div class="swiper-slide">
                                <f7-link class="display-block" style="width: 100%; height: 33vw; border-radius: 5px; background: #ccc; box-shadow: 0 0 8px rgba(0, 0, 0, 0.05);">

                                </f7-link>
                            </div>
                        </div>
                        <div class="swiper-pagination"></div>
                    </div>
                </div>
            </div> -->
            <div class="block no-margin bg-color-white no-padding">
                <div class="list no-margin">
                    <ul>
                        <li class="item-divider">Cá nhân</li>
                        <li>
                            <a href="#" class="item-link item-content">
                                <div class="item-media" style="min-width: 30px"><i class="fa fa-diamond" aria-hidden="true"></i></div>
                                <div class="item-inner no-margin-left">
                                    <div class="item-title">
                                        <div class="item-header fs-15">Ưu đãi cho thành viên</div>
                                        <div class="item-footer">Còn 1138 điểm để thành Thành viên Vàng</div>
                                    </div>
                                </div>
                            </a>
                        </li>
                        <li>
                            <a href="#" class="item-link item-content">
                                <div class="item-media" style="min-width: 30px"><i class="fa fa-credit-card-alt" aria-hidden="true"></i></div>
                                <div class="item-inner no-margin-left">
                                    <div class="item-title">
                                        <div class="item-header fs-15">Hoa hồng từ liên kết</div>
                                        <div class="item-footer">Tích được 1.000.000đ</div>
                                    </div>
                                </div>
                            </a>
                        </li>
                        <li>
                            <a href="/edit-profile/" class="item-link item-content">
                                <div class="item-media" style="min-width: 30px"><i class="fa fa-cog" aria-hidden="true"></i></div>
                                <div class="item-inner no-margin-left">
                                    <div class="item-title">
                                        <div class="item-header fs-15">Cập nhật tài khoản</div>
                                        <div class="item-footer"></div>
                                    </div>
                                </div>
                            </a>
                        </li>
                        <li>
                            <a href="/lien-ket-tk-xh/" class="item-link item-content text-color-black">
                                <div class="item-media" style="min-width: 30px"><i class="fa fa-share-alt" aria-hidden="true"></i></div>
                                <div class="item-inner no-margin-left">
                                    <div class="item-title">
                                        <div class="item-header fs-15">Liên kết tài khoản</div>
                                        <!-- <div class="item-footer">Đang sử dụng Tiếng Việt</div> -->
                                    </div>
                                    <div class="item-after">
                                        <!-- <div class="display-flex justify-content-space-evenly">
                                            <a class="item-link" href=""><img style="width: 24px; padding: 5px" src="./../img/fb.png" alt=""></a>
                                            <a class="item-link" href=""><img style="width: 24px; padding: 5px" src="./../img/gg.png" alt=""></a>
                                            <a class="item-link" href=""><img style="width: 24px; padding: 5px" src="./../img/zalo.png" alt=""></a>
                                            <a class="item-link" href=""><img style="width: 24px; padding: 5px" src="./../img/instagram-new.png" alt=""></a>
                                        </div> -->
                                    </div>
                                </div>
                            </a>
                        </li>
                        <li>
                            <a class="item-content text-color-black">
                                <div class="item-media" style="min-width: 30px"><i class="fa fa-life-ring" aria-hidden="true"></i></div>
                                <div class="item-inner no-margin-left">
                                    <div class="item-title">
                                        <div class="item-header fs-15">Hỗ trợ cho bạn</div>
                                        <!-- <div class="item-footer">Đang sử dụng Tiếng Việt</div> -->
                                    </div>
                                    <div class="item-after">
                                        <div class="display-flex justify-content-space-evenly">
                                            <a class="item-link" href="" style="padding: 5px; margin-right: 10px"><i class="fa fa-phone-square fa-2x" aria-hidden="true"></i></a>
                                            <a class="item-link" href="" style="padding: 5px; margin-right: 10px"><i class="fa fa-comments fa-2x" aria-hidden="true"></i></a>
                                            <a class="item-link" href="" style="padding: 5px"><i class="fa fa-envelope fa-2x" aria-hidden="true"></i></a>
                                        </div>
                                    </div>
                                </div>
                            </a>
                        </li>
                    </ul>
                </div>
            </div>
            <div class="block no-margin bg-color-white no-padding">
                <div class="list no-margin">
                    <ul>
                        <li class="item-divider">Thông tin chung</li>
                        <li>
                            <a href="#" class="item-link item-content">
                                <div class="item-media" style="min-width: 30px"><i class="fa fa-shield" aria-hidden="true"></i></div>
                                <div class="item-inner no-margin-left">
                                    <div class="item-title fs-15">Chính sách bảo mật</div>
                                </div>
                            </a>
                        </li>
                        <li>
                            <a href="#" class="item-link item-content">
                                <div class="item-media" style="min-width: 30px"><i class="fa fa-info-circle" aria-hidden="true"></i></div>
                                <div class="item-inner no-margin-left">
                                    <div class="item-title fs-15">Điều khoản dịch vụ</div>
                                </div>
                            </a>
                        </li>
                        <!-- <li>
                            <a href="#" class="item-link item-content">
                                <div class="item-media" style="min-width: 30px"><i class="fa fa-life-ring" aria-hidden="true"></i></div>
                                <div class="item-inner no-margin-left">
                                    <div class="item-title fs-15">Trung tâm trợ giúp</div>
                                </div>
                            </a>
                        </li> -->
                        <li>
                            <a href="#" class="item-link item-content">
                                <div class="item-media" style="min-width: 30px"><i class="fa fa-language" aria-hidden="true"></i></div>
                                <div class="item-inner no-margin-left">
                                    <div class="item-title">
                                        <div class="item-header fs-15">Thay đổi ngôn ngữ</div>
                                    </div>
                                    <div class="item-after">Tiếng Việt</div>
                                </div>
                            </a>
                        </li>
                        <li>
                            <div class="item-content">
                                <div class="item-media" style="min-width: 30px"><i class="fa fa-sign-out" aria-hidden="true"></i></div>
                                <div class="item-inner no-margin-left">
                                    <div class="item-title">Đăng xuất</div>
                                </div>
                            </div>
                        </li>
                        <li>
                            <div class="item-content">
                                <div class="item-media" style="min-width: 30px"><i class="fa fa-bell" aria-hidden="true"></i></div>
                                <div class="item-inner no-margin-left">
                                    <div class="item-title">Phiên bản đang dùng</div>
                                    <div class="item-after">1.0.0</div>
                                </div>
                            </div>
                        </li>

                    </ul>
                </div>
            </div>
        </f7-tab>
    </f7-tabs>
</f7-page>
</template>

<script>
var dateFns = require('date-fns');
import NavBar from "./../component/NavBar.vue";
import ToolBar from "./../component/ToolBar.vue";
import apiEndPoint from "./../../apiEndpoint.js";
import {
    EventLogin
} from "../event-login.js";
import axios from "axios";
export default {
    components: {
        NavBar,
        ToolBar,
    },
    data() {
        return {
            isBottom: true,
            tabs: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10],
            showNavGame: true,
            sheetOpened: false,
            actionGridOpened: false,
        };
    },
    updated() {

    },

    methods: {
        onPageBeforeRemove() {
            const self = this;
            if (self.popup) self.popup.destroy();
            if (self.popover) self.popover.destroy();
        },
        onPageInit() {
            let self = this;
            self.lazy = self.$f7.lazy.create({
                lazy: {
                    threshold: 50,
                    sequential: false,
                },
            });
            self.mySwiper0 = self.$f7.swiper.create(".demo-swiper0", {
                pagination: {
                    el: ".swiper-pagination",
                    type: "custom",
                    clickable: true,
                },
                navigation: {
                    nextEl: '.swiper-button-next',
                    prevEl: '.swiper-button-prev',
                },
                speed: 1000,
                autoplay: {
                    delay: 3000,
                },
                slidesPerView: 1,
                observer: true,
                observeParents: true,
                spaceBetween: 10,
            });
            self.mySwiper1 = self.$f7.swiper.create(".demo-swiper1", {
                pagination: {
                    el: ".swiper-pagination",
                    type: "custom",
                    clickable: true,
                },
                navigation: {
                    nextEl: '.swiper-button-next',
                    prevEl: '.swiper-button-prev',
                },
                speed: 1000,
                autoplay: {
                    delay: 3000,
                },
                slidesPerView: 2,
                observer: true,
                observeParents: true,
                spaceBetween: 10,
            });
            self.mySwiper2 = self.$f7.swiper.create(".demo-swiper2", {
                pagination: {
                    el: ".swiper-pagination",
                    type: "custom",
                    clickable: true,
                },
                navigation: {
                    nextEl: '.swiper-button-next',
                    prevEl: '.swiper-button-prev',
                },
                // speed: 1000,
                // autoplay: {
                //     delay: 3000,
                // },
                slidesPerView: 'auto',
                observer: true,
                observeParents: true,
                spaceBetween: 10,
            });
            self.mySwiper3 = self.$f7.swiper.create(".demo-swiper3", {
                pagination: {
                    el: ".swiper-pagination",
                    type: "custom",
                    clickable: true,
                },
                navigation: {
                    nextEl: '.swiper-button-next',
                    prevEl: '.swiper-button-prev',
                },
                // speed: 1000,
                // autoplay: {
                //     delay: 3000,
                // },
                slidesPerView: 'auto',
                observer: true,
                observeParents: true,
                spaceBetween: 10,
            });
        }
    },
    async created() {}
}
</script>
