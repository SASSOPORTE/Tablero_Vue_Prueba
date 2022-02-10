<template class="ag-theme-balham-dark">
  <div >
  <!-- O puedes comentar una gran cantidad de líneas. -->
  <ag-grid-vue    
    style="width: 1800px; height: 500px" 
    class="ag-theme-balham-dark"
    :rowData="rowData" 
    :columnDefs="columnDefs"
    :allow-column-resizing="true"
    :defaultColDef="defaultColDef"
    :column-auto-width="true" 
    :colResizeDefault="colResizeDefault"    
    :rowDragManaged="true"
    :suppressMoveWhenRowDragging="true"  
    :statusBar="statusBar"
    :sideBar="sideBar"
    :columnHoverHighlight="true"  
    @grid-ready="onGridReady"

    >

  </ag-grid-vue>

  </div>
  
</template>

<script>
import { AgGridVue } from "ag-grid-vue";
//import FullWidthCellRenderer from './fullWidthCellRendererVue.js';

export default {
  name: "App",
  data() {
    return {
      columnDefs: null,
      rowData: null,
      defaultColDef: { resizable: true },
              
    };
  },
  components: {
    AgGridVue,  
   
  },
  beforeMount() {

    this.columnDefs = [
      { field: "Responsable_Actual", sortable: true, filter: true , editable:true, rowDrag: true },
      { field: "Identificación", sortable: true, filter: true , editable:true },
      { field: "Nombres", sortable: true, filter: true , editable:true },
      { field: "Datos_Contacto", sortable: true, filter: true  },
      { field: "Reportes", sortable: true, filter: true , editable:true },
      { field: "Detalles", sortable: true, filter: true , editable:true  },
      { field: "Documentos", sortable: true, filter: true , editable:true },
      { field: "Gestión_Total", sortable: true, filter: true , editable:true },
      { field: "Agendamiento", sortable: true, filter: true , editable:true  },
      { field: "Auditoria", cellRendered: "Auditoria"},

    ];

    this.rowData = [
      { Responsable_Actual: "Marlon Nivia",  Identificación: "C.C: 3.500.550" , Nombres: "Claudia Patricia Garzon Ramirez", Datos_Contacto: '´\f',
      Reportes: "Imagen ", Detalles: "Imagen ", Documentos: "Imagen" , Gestión_Total: "Imagen", Agendamiento: "Imagen"  },
      { Responsable_Actual: "Bryam Garzon",  Identificación: "C.C: 4.500.960" , Nombres: "Patricia Porras",Datos_Contacto: '´\f',
      Reportes: "Imagen ", Detalles: "Imagen ", Documentos: "Imagen" , Gestión_Total: "Imagen", Agendamiento: "Imagen" },
      { Responsable_Actual: "Diego Garzon",  Identificación: "C.C: 8.500.850", Nombres: "Camilo Garzon Ramirez",Datos_Contacto: '´\f',
      Reportes: "Imagen ", Detalles: "Imagen ", Documentos: "Imagen" , Gestión_Total: "Imagen", Agendamiento: "Imagen" },
      { Responsable_Actual: "Cesar Devia", Identificación: "C.C: 6.500.420" , Nombres: "Angie Paola Devia Gaita",Datos_Contacto: '´\f',
      Reportes: '\f068', Detalles: '\f068', Documentos: "Imagen" , Gestión_Total: "Imagen", Agendamiento: "Imagen"  },
    ];
  },
  created() {
    this.rowSelection = 'multiple';
    this.statusBar = {
      statusPanels: [
        { statusPanel: 'agTotalAndFilteredRowCountComponent', align: 'left' },
        { statusPanel: 'agTotalRowCountComponent', align: 'center' },
        { statusPanel: 'agFilteredRowCountComponent' },
        { statusPanel: 'agSelectedRowCountComponent' },
        { statusPanel: 'agAggregationComponent' },
      ],
    };
    this.sideBar = {
      toolPanels: [
        {
          id: 'columns',
          labelDefault: 'Columns',
          labelKey: 'columns',
          iconKey: 'columns',
          toolPanel: 'agColumnsToolPanel',
        },
        {
          id: 'filters',
          labelDefault: 'Filters',
          labelKey: 'filters',
          iconKey: 'filter',
          toolPanel: 'agFiltersToolPanel',
        },
      ],
    };   
  },
  methods: {

  },
 };
</script>



<style lang="scss">
  @import "~ag-grid-community/dist/styles/ag-grid.css";
  @import "~ag-grid-community/dist/styles/ag-theme-balham-dark.css";

</style>