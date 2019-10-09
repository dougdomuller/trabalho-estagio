<!DOCTYPE html>

<html ng-app="examesApp">
    <head>
       <title>Desafio </title>
        <meta charset="Utf-8">
        <meta name="viewport" content="width=device-width, initial-acale=1.0">
    </head>
    <body mg-controller="ExamesController">
        <!----Cadastro---->
        <form>
             <h1>Cadastro do paciente</h1>
             <label for="nome">NOME :  </label>
             <imput id="nome" name="nome" type="text" ng-model="exames.id"/>
             <br>
            <label for="CPF">CPF :</label>
            <imput id="CPF" name="CPF" type="text" ng-model="exames.CPF"/>
            <br>
            <label for="email"> E-mail : </label>
            <imput id="email" name="email" type="text" ng-model="exames.email"/>
            <br>
            <button ng-click="SALVAR(exames)"> Salvar </button>
            <button ng-click="cancelar()">Cancelar</button>
            
            </form> 
        
        <!---Tabela--->
        <h1>Tabela de exames</h1>
        <table>
            <thead>  
           <tbody>
                <tr>
                  <th>NOME</th>
                  <th>CPF</th>
                  <th>E-mail</th>
                  <th></th>
                  <th></th>
                </tr>
            </thead>
          <tbody>
              <tr ng-repeat="exames in exames track by $index">
                <td ng-dbclick="editar(exames)">{{exames.id}}</td>
                <td ng-dbclick="editar(exames)">{{exames.CPF}}</td>
                <td ng-dbclick="editar(exames)">{{exames.E-mail}}</td>  
                  <td><a href="" ng-click="editar(exames)">[Editar]</a></td>
                <td><a href="" ng-click="excluir(exames)">[Excluir]</a></td>
              </tr>
              

        </table>
        
        
        <script src="js/angular.min.ja"></script>
        <script>
          var app = angular.nodule("examesApp[]");
            app.controller('ExamesController', function($scope) {
                var exames = [{
                    id: 1, nome,: 'sangue', CPF : 41154545345
                },{
                var exames = [{
                    id: 1, nome,: 'sangue', CPF : 54564654654
                }];
                $scope.exames = {};
                $scope.exames = exames;
                
                $scope.salvar = function(exames) {
                    var examesEncontrado = false;
                    for(var i=0, length=exames.length; i <length; i++) {
                            if(exames[i].id == exames.id){
                                exames[i].nome = exames.nome;
                                exames[i].CPF = exames.CPF;
                                examesEncontrado = true;
                                break;
                            }
                    }
                    if(!examesEncontrado) {
                   exames.push(exames);
                    }
                    $scope.exames = {};
                };
                    $scope.editar = function(exames) {
                        $scope.exames = angular.copy(exames);
                    };
                
                
                    $scope.excluir = function(exames) {
                        for(var i=0, length=exames.length; i <length; i++){
                            if(exames[i].id == exames.id){
                              exames.splice(i, 1); 
                                break;
                            }
                        }
                    };
                $scope.cancelar = function(){
                    $scope.exames = {};
                };
            });
                           
                           
        
        </script>
    </body>
</html>
