<!DOCTYPE html>
<html>
<head>
  <title>Nordic AI Angels</title>
  <link rel="stylesheet" href="https://cdn.datatables.net/1.13.6/css/jquery.dataTables.min.css">
</head>
<body>
  <table id="angels" class="display"></table>
  <script src="https://code.jquery.com/jquery-3.7.0.min.js"></script>
  <script src="https://cdn.datatables.net/1.13.6/js/jquery.dataTables.min.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/papaparse@5.4.1/papaparse.min.js"></script>
  <script>
    Papa.parse('data/top-nordic-ai-angels.csv', {
      download: true,
      header: true,
      complete: function(results) {
        $('#angels').DataTable({ data: results.data, columns: Object.keys(results.data[0]).map(k => ({ title: k, data: k })) });
      }
    });
  </script>
</body>
</html>
