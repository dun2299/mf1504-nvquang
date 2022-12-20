<template>
  <div class="page-table">
    <div class="table-container">
      <table class="m-table" id="tblEmployee">
        <thead>
          <tr>
            <th class="table-checkbox">
              <label class="m-table-checkbox  m-margin-lr-16">
                <input type="checkbox" class="m-input-checkbox" />
                <span class="m-checkbox">
                  <span class="m-checkbox-inner">
                    <div class="m-icon m-icon-16 m-icon-checkbox-active"></div>
                  </span>
                </span>
              </label>
            </th>
            <th class="table-id">
              MÃ NHÂN VIÊN
            </th>
            <th class="table-name">
              TÊN NHÂN VIÊN
            </th>
            <th class="table-gender">
              GIỚI TÍNH
            </th>
            <th class="table-dob text-center">
              NGÀY SINH
            </th>
            <th class="table-id-card" title="Số chứng minh nhân dân">
              SỐ CMND
            </th>
            <th class="table-position">
              CHỨC DANH
            </th>
            <th class="table-work">
              TÊN ĐƠN VỊ
            </th>
            <th class="table-bank-id">
              SỐ TÀI KHOẢN
            </th>
            <th class="table-bank-name">
              TÊN NGÂN HÀNG
            </th>
            <th class="table-bank-place">
              CHI NHÁNH NGÂN HÀNG
            </th>
            <th class="table-func text-center">
              CHỨC NĂNG
            </th>
          </tr>
        </thead>

        <tbody>
          <tr v-for="(employee) in employees" :key="employee.EmployeeId"
            @dblclick="insertEmployeeHandle(employee.EmployeeId)">
            <td class="table-checkbox">
              <label class="m-table-checkbox  m-margin-lr-16">
                <input type="checkbox" class="m-input-checkbox" />
                <span class="m-checkbox">
                  <span class="m-checkbox-inner">
                    <div class="m-icon m-icon-16 m-icon-checkbox-active"></div>
                  </span>
                </span>
              </label>
            </td>
            <td class="table-id" table-property-name="EmployeeCode">{{ employee.EmployeeCode }}</td>
            <td class="table-name">{{ employee.EmployeeName }}</td>
            <td class="table-gender">{{ employee.GenderName }}</td>
            <td class="table-dob text-center">{{ convertDate(employee.DateOfBirth) }}</td>
            <td class="table-id-card">{{ employee.IdentityNumber ? employee.IdentityNumber : "" }}</td>
            <td class="table-position">{{ employee.PositionName ? employee.PositionName : "" }}</td>
            <td class="table-work">{{ employee.DepartmentName ? employee.DepartmentName : "" }}</td>
            <td class="table-bank-id">{{ employee.BankAccountNumber ? employee.BankAccountNumber : "" }}
            </td>
            <td class="table-bank-name">{{ employee.BankName ? employee.BankName : "" }}</td>
            <td class="table-bank-place">{{ employee.BankBranchName ? employee.BankBranchName : "" }}</td>
            <td class="table-func text-center m-flex">
              <div class="m-dropdown">
                <button class="m-dropdown-type-feature m-dropdown-button-text m-edit-employee">
                  <div class="m-button-text " @click="insertEmployeeHandle(employee.EmployeeId)">Sửa</div>
                </button>
                <button class="m-dropdown-type-feature m-dropdown-button-icon m-dropdown-icon-emp">
                  <div class="m-button-text">
                    <div class="m-icon m-icon-16 m-icon-arrow-down-blue"></div>
                  </div>
                </button>

              </div>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
  <Teleport to="body">
    <div class="m-dropdown-menu m-dropdown-emp">
      <ul class="m-dropdown-menu-items">
        <li class="m-dropdown-item">
          <a class="m-dropdown-item-link">Nhân bản</a>
        </li>
        <li class="m-dropdown-item m-item-delete">
          <a class="m-dropdown-item-link">Xóa</a>
        </li>
        <li class="m-dropdown-item">
          <a class="m-dropdown-item-link">Ngừng sử dụng</a>
        </li>
      </ul>
    </div>
  </Teleport>
</template>

<script>
import axios from "axios"

export default {
  name: "MTable",
  props: {
    isReloadData: {
      type: Boolean,
      default: false
    }
  },
  emits: ['trDbl', 'loadDataDone'],
  data() {
    return {
      employees: [],
    }
  },
  methods: {
    /**
     * Định dạng ngày tháng để hiển thị vào bảng dữ liệu
     * Author: QuangNV (15/12/2022)
     */
    convertDate(date) {
      try {
        if (date) {
          date = new Date(date)
          let day, month, yeah;
          if (date.getDate() > 9) {
            day = date.getDate();
          } else {
            day = '0' + date.getDate();
          }
          if ((date.getMonth() + 1) > 9) {
            month = (date.getMonth() + 1);
          } else {
            month = '0' + (date.getMonth() + 1);
          }
          yeah = date.getFullYear();
          return `${day}/${month}/${yeah}`
        } else {
          return ""
        }
      } catch (error) {
        console.log(error);
      }
    },

    /**
     * Xử lý khi double click vào row
     *  Author: QuangNV (16/12/2022)
     */
    insertEmployeeHandle(employeeId) {
      this.$emit('trDbl', employeeId)
    },

    /**
     * Gọi Api và trả về dữ liệu
     * Author: QuangNV (16/12/2022)
     */
    fetchAll() {
      axios.get('https://amis.manhnv.net/api/v1/Employees')
        .then(res => {
          this.employees = res.data;
          this.$emit('loadDataDone', false)
        })
    }
  },
  created() {
    this.fetchAll()
  },

  watch: {
    isReloadData: {
      immediate: true,
      handler() {
        this.fetchAll()
      }
    }
  }

}



</script>


