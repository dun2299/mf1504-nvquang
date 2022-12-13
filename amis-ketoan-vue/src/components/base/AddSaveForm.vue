<template>
    <div class="dialog" id="addAndInsertForm" style="display:block">
        <div class="dialog-container form">
        <div class="dialog-close">
            <div class="m-icon m-icon-24 help-icon" title="Help"></div>
            <div class="m-icon m-icon-24 close-icon" title="Close"></div>
        </div>
        <div class="dialog-header form-header">
            <div class="header-title">Thông tin nhân viên</div>
            <div class="checkbox m-flex m-margin-lr-16">
                <label class="m-table-checkbox  m-margin-lr-16">
                    <input type="checkbox" class="m-input-checkbox" />
                    <span class="m-checkbox">
                        <span class="m-checkbox-inner">
                        <div class="m-icon m-icon-16 m-icon-checkbox-active"></div>
                        </span>
                    </span>
                </label>
            <div class="checkbox-title">Là khách hàng</div>
            </div>
            <div class="checkbox m-flex">
            <div class="checkbox-icon">
                <label class="m-table-checkbox  m-margin-lr-16">
                    <input type="checkbox" class="m-input-checkbox" />
                    <span class="m-checkbox">
                        <span class="m-checkbox-inner">
                            <div class="m-icon m-icon-16 m-icon-checkbox-active"></div>
                        </span>
                    </span>
                </label>
            </div>
            <div class="checkbox-title">Là nhà cung cấp</div>
            </div>
        </div>
        <div class="form-content">
            <div class="m-flex" >
                <div style="width: 50%;background-color: #fff;padding-right: 10px;">
                    <div class="m-flex">
                        <div class="div" style="display: block; width: 150px;">
                            <MInput fieldLabel="Mã nhân viên" propertyName="EmployeeCode"></MInput>
                        </div>
                        <div class="div" style="display: block; flex: 1;">
                            <MInput fieldLabel="Tên nhân viên" propertyName="EmployeeName"></MInput>
                        </div>
                    </div>
                    
                    <div class="m-input-box">
                        <label for="" class="m-input-label">Đơn vị <div class="m-input-title-require">&nbsp;*</div></label>
                        <div class="dropdown" >
                            <select name="" property-name="DepartmentId" id="employeeDepartment" class="m-input m-dropdown-select" m-required field-label="Đơn vị">
                                <option value="1" selected>10 bản ghi trên 1 trang</option>
                                <option value="2">20 bản ghi trên 1 trang</option>
                                <option value="3">30 bản ghi trên 1 trang</option>
                            </select>
                        </div>
                    </div>
                    <div class="m-input-box" style="display: block;">
                        <label for="" class="m-input-label">Chức danh</label>
                        <div class="dropdown" >
                            <select name="" id="employeePosition" class="m-input m-dropdown-select" property-name="PositionId">
                                <option value="1" selected>10 bản ghi trên 1 trang</option>
                                <option value="2">20 bản ghi trên 1 trang</option>
                                <option value="3">30 bản ghi trên 1 trang</option>
                            </select>
                        </div>
                    </div>
                </div>
            
                <div style="flex: 1;">
                    <div class="m-flex">
                        <div class="m-input-box" style="display: block; width: 150px;">
                            <label for="" class="m-input-label">Ngày sinh</label>
                            <input type="date" class="m-input" id="dob" property-name="DateOfBirth">
                        </div>
                        <div class="radio-box" style="display: block; flex: 1;">
                            <label for="" class="m-input-label">Giới tính</label>
                            <div class="radio-list" property-name="Gender" id="gender">
                                <label class="m-con-radio">
                                    <input type="radio" class="m-input-radio" value="0" name="gender" />
                                    <span class="m-radio">
                                        <span class="m-radio-border"></span>
                                        <span class="m-radio-circle"></span>
                                    </span>
                                    <span class="m-radio-label">Nam</span>
                                </label>
                                <label class="m-con-radio">
                                    <input type="radio" class="m-input-radio" value="1" name="gender" />
                                    <span class="m-radio">
                                        <span class="m-radio-border"></span>
                                        <span class="m-radio-circle"></span>
                                    </span>
                                    <span class="m-radio-label">Nữ</span>
                                </label>
                                <label class="m-con-radio">
                                    <input type="radio" class="m-input-radio" value="2" name="gender" />
                                    <span class="m-radio">
                                        <span class="m-radio-border"></span>
                                        <span class="m-radio-circle"></span>
                                    </span>
                                    <span class="m-radio-label">Khác</span>
                                </label>
                            </div>
                        </div>
                    </div>  
                    <div class="m-flex">
                        <div style="display: block; flex: 1;">
                            <MInput fieldLabel="Số CMTND" propertyName="IdentityNumber" title="Số chứng minh thư nhân dân"></MInput>
                        </div>
                        <div style="display: block; width: 150px;">
                            <MInput fieldLabel="Ngày cấp" propertyName="IdentityDate"></MInput>
                        </div>
                    </div>
                    <MInput fieldLabel="Nơi cấp" propertyName="IdentityPlace"></MInput>
                </div>
            </div>
            <div>
                <MInput fieldLabel="Địa chỉ" propertyName="Address"></MInput>
            </div>
            <div style="width:75%">
            <div class="m-flex" style="width: 100%;">
                <div style="display: block; width: 33%;">
                    <MInput fieldLabel="ĐT di động" propertyName="TelephoneNumber"></MInput>
                </div>
                <div style="display: block; width: 33%;">
                    <MInput fieldLabel="ĐT cố định" propertyName="PhoneNumber"></MInput>
                </div>
                <div style="display: block; width: 33%;">
                    <MInput fieldLabel="Email" propertyName="Email"></MInput>
                </div>
            </div>
            <div class="m-flex" style="width: 100%;">
                <div style="display: block; width: 33%;">
                    <MInput fieldLabel="Tài khoản ngân hàng" propertyName="Email"></MInput>
                </div>
                <div style="display: block; width: 33%;">
                    <MInput fieldLabel="Tên ngân hàng" propertyName="Email"></MInput>
                </div>
                <div style="display: block; width: 33%;">
                    <MInput fieldLabel="Chi nhánh" propertyName="Email"></MInput>
                </div>
            </div>
            </div>
        </div>
        <div class="form-footer" >
            <div class="footer-right">
                <MButton class="dialog-btn primary-btn accept-btn" text="Cất và thêm"></MButton>
                <MButton class="m-btn dialog-btn lower-btn cancel-btn" text="Cất"></MButton>
            </div>
            <div class="footer-left">
                <MButton class=" dialog-btn lower-btn" text="Hủy"></MButton>
            </div>
        </div>
        </div>
    </div>
</template>

<script>
import MInput from './MInput.vue';
import MButton from './MButton.vue';
export default {
    name: "AddSaveForm",
    components: {
        MInput,
        MButton
    }
}
</script>

<style scoped>
    @import url(../../css/style.css);
</style>