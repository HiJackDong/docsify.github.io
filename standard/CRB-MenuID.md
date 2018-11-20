## CRB 笔记

#### MenuID

##### 入库

| MenusID                                  | 说明                      |
| ---------------------------------------- | ------------------------- |
| wm_shell_list_asn_receipts Toolbar       | 收货单Toolbar             |
| ASN Actions                              | 收货单行动菜单            |
| wm_Asnreceipt_report_menu                | 收货单报表菜单            |
| wm_receiptdetail_toggle_view Toolbar     | 收货单明细Toolbar         |
| wm_shell_list_asn_receipt_detail Toolbar | ASN/收货明细Toolbar       |
| wm_verifyclose_asnpo_action              | 验证并结算按钮            |
| wm_Asnreceipt_detail_Action              | 收货单明细Toolbar操作按钮 |

入库刷新按钮事件

1. Extensions

| Event                | Extension      |
| -------------------- | -------------- |
| clickEvent (REFRESH) | GetFocusOfSlot |

2. Navigation

| Container                  | BIO Source     | BIO Path               | Content                                      |
| -------------------------- | -------------- | ---------------------- | -------------------------------------------- |
| wms_list_shell.list_slot_1 | From Extension |                        | receipt - WMS_TBGRP_SHELL                    |
| wms_list_shell.list_slot_2 | From Extension | receipt:RECEIPTDETAILS | receiptdetail - wm_receiptdetail_toggle_view |

##### 出库

| MenusID                                  | 说明          |
| ---------------------------------------- | ----------- |
| wm_list_shell_shipmentorder Toolbar      | 出库单Toolbar  |
| wm_shipmentorder_actions                 | 出库订单操作按钮    |
| ShipmentOrderReports                     | 出库单报表       |
| wm_shipmentorderdetail_toggle_view Toolbar | 出库明细Toolbar |

出库刷新按钮事件

1. Extensions

| Event                | Extension      |
| -------------------- | -------------- |
| clickEvent (REFRESH) | GetFocusOfSlot |

2. Navigation

| Container                               | BIO Source     | Content                                         |
| --------------------------------------- | -------------- | ----------------------------------------------- |
| wm_list_shell_shipmentorder.list_slot_1 | From Extension | wm_orders - WMS_TBGRP_SHELL_SHIPMENTORDER       |
| wm_list_shell_shipmentorder.list_slot_2 | From Extension | wm_orders - wm_shipment_orderdetail_toggle_view |

##### 内部转移

| MenusID                                 | 说明          |
| --------------------------------------- | ----------- |
| wm_list_shell_internal_transfer Toolbar | 内部转移Toolbar |
| InternalTransferActions                 | 操作按钮Menu    |

##### 计费

| MenusID                 | 说明   |
| ----------------------- | ---- |
| Billing_Facility_Charge | 计费菜单 |

##### 库存余额

| MenusID                                  | 说明             |
| ---------------------------------------- | ---------------- |
| wm_list_shell_inventory_balances Toolbar | 库存余额Toolbar  |
| wm_inventory_balance_base_list_form      | 库存余额列表form |

##### 导出按钮

export

| Event                | Extension          | Priority |
| -------------------- | ------------------ | -------- |
| onclick (export)     | CCFSendDataRequest | 100      |
| ccfSendData (export) | ExportToXLS        | 102      |

##### 波次创建

```java
module:wm_wp_query_builder_ui
//波次筛选界面
wm_wp_query_builder_shell_filter Toolbar
menu:wm_wp_query_builder_filter_actions

//波次筛选出订单后，波次创建界面
wm_wp_query_builder_shell_ordersl Toolbar
wm_wp_query_builder_orders_actions

//保存筛选节目
wp_saved_filters_shell_filter_detail Toolbar
wp_saved_filters_actions
```

##### Form 名称汇总

##### 波次

```java
// 查询组建器订单筛选页面form
wm_wp_query_builder_initial_screen    BIO:querybuildertemp
// 查询组建器订单筛选后的表头form
wm_wp_query_builder_shipment_orders_totals_screen_1
```