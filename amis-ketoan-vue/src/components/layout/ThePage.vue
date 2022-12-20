<template>
  <div class="page">
    <div class="page-header">
      <div class="page-header-title">Nhân viên</div>

      <div class="page-header-button">
        <MButton @click="onAddEmployeeClick" text="Thêm nhân viên mới"></MButton>
      </div>
    </div>
    <div class="page-content">
      <div class="page-toolbar">
        <MInputIcon></MInputIcon>
        <div class="m-icon m-icon-24 refresh-icon" style="margin: 0 10px;" id="refresh-btn" @click="onReload"></div>
      </div>
      <MTable :isReloadData="isReloadData" @tr-dbl="onInsertEmployee" @loadDataDone="loadDataDone"></MTable>
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
  <AddSaveForm v-if="isFormShow" @cancel="onToggleForm" :employeeSelectedId="employeeSelectedId"
    @saveBtnOnClick="btnSaveOnClick"></AddSaveForm>
  <TheLoading v-if="isLoading"></TheLoading>

</template>

<script>
import MButton from '../base/MButton.vue';
import MInputIcon from '../base/MInputIcon.vue';
import MTable from '../base/MTable.vue';
import AddSaveForm from '../base/AddSaveForm.vue';
import TheLoading from '../TheLoading.vue';
export default {
  name: "ThePage",
  data() {
    return {
      isFormShow: false,
      employeeSelectedId: null,
      isReloadData: false,
      isLoading: true
    }
  },
  components: {
    MButton,
    MInputIcon,
    MTable,
    AddSaveForm,
    TheLoading,
  },
  methods: {
    /**
     * Ẩn hiện form 
     * Author: QuangNV (15/12/2022)
     */
    onToggleForm() {
      this.isFormShow = !this.isFormShow;
    },

    /**
     * Xử lý sự kiện click vào thêm nhân viên
     * Author: QuangNV (16/12/2022)
     */
    onAddEmployeeClick() {
      this.onToggleForm();
      this.employeeSelectedId = null;
      console.log(this.employeeSelectedId);
    },
    /**
     * Xử lý sự kiện dbl click và nhấn sửa
     * Author: QuangNV (16/12/2022)
     */
    onInsertEmployee(employeeId) {
      this.onToggleForm();
      console.log(employeeId);
      this.employeeSelectedId = employeeId;
    },

    /**
     * Xử lý logic khi ấn cất
     * Author: QuangNV (20/12/2022)
     */
    btnSaveOnClick(isLoadData, isShowForm) {
      this.isReloadData = isLoadData;
      this.isLoading = true;
      this.isFormShow = isShowForm;
    },

    loadDataDone(isLoadData) {
      this.isLoading = isLoadData;
      this.isReloadData = false;
      console.log(this.isLoading)
    },

    onReload() {
      this.isLoading = true;
      this.isReloadData = true;
      console.log(1)
    }
  }
}
</script>

