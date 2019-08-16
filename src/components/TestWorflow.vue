<template>
<vue-mermaid :nodes="data" type="graph TB" @nodeClick="editNode"></vue-mermaid>
</template>


<script>
  export default {
    data: function() {
      return {
        data: [
          {
            id: "1",
            text: "   ",
            link: "---",
            edgeType: "circle",
            editable: true,
            next:["2", "3"],
            style: "fill:#f9f,stroke:#333,stroke-width:4px"
          },
          { id: "2", text: "Pause" },
          { id: "3", text: "Terminée", next: ["4"], link: "-- blabla -->" },
          { id: "4", text: "Débrief", next: ["5", "3"] },
          { id: "5", text: "Double Débrief", next: ["6"] },
          { id: "6", text: "F", edgeType: "circle"}
        ]
      };
    },
    methods: {
      editNode(nodeId) {
        alert(nodeId);
      }
    }
  };
</script>


