<template>
    <div class="page">
                <div class="page-header">
                    <div class="page-header-title">Nhân viên</div>
                    <div class="page-header-button">
                        <MButton text="Thêm nhân viên mới"></MButton>
                    </div>
                </div>
                <div class="page-content">
                    <div class="page-toolbar">
                        <MInputIcon></MInputIcon>
                        <div class="m-icon m-icon-24 refresh-icon" style="margin: 0 10px;" id="refresh-btn"></div>
                    </div>
                    <MTable></MTable>
                    <div class="page-paging">
                        <div class="total-record"></div>
                        <div class="right-paging">
                            <div class="m-record-in-page">
                                <div class="m-combo-box">
                                    <div class="m-combo-main-content">
                                        <div class="m-selected-options">
                                            <input type="text" class="m-combo-input" readonly="true" autofocus value="10 bản ghi trên 1 trang" />
                                        </div>
                                        <div class="m-combo-action m-select-record">
                                            <div class="m-btn-dropdown">
                                                <div class="m-icon m-icon-16 m-icon-arrow-dropdown m-dropdown-close">
                                                </div>
                                            </div>
                                        </div>
                                    </div>
                                </div>
                            </div>
                            <div class="pagination">
                                <div class="page-btn disable-btn">trước</div>
                                <div class="page-btn active">1</div>
                                <div class="page-btn">2</div>
                                <div class="page-btn">3</div>
                                <div class="page-btn">...</div>
                                <div class="page-btn">42</div>
                                <div class="page-btn">sau</div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
</template>

<script>
import MButton from '../base/MButton.vue';
import MInputIcon from '../base/MInputIcon.vue';
import MTable from '../base/MTable.vue';
export default {
    name: "ThePage",
    components: {
        MButton,
        MInputIcon,
        MTable
    }
}
</script>

<style scoped>
    @import url(../../css/style.css);
</style>