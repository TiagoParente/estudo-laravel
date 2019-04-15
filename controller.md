# Controller
* Caminho dos controller: App\Http\Controllers.
* Comando para criar os controllers: **php artisan make:controller NomeController**.
* Exemplo de Rotas utilizando controller:

> Route::get('/', 'NomeController@index');
         
*Onde o 'index' é um metodo que existe no meu controller NomeController e retorna para um view.*

 - Para organizar os controllers em subpastas é necessário fazer as
   seguintes alterações:
 - Mudar o name space de **App\Http\Controllers** para **App\Http\Controllers\NomeDaPasta**.
 - Dar um **USE** em **App\Http\Controllers\Controller**.
 - Usar o **Route::group** com o parâmetro de namespace, igual no exemplo que esta na parte de explicações sobre rotas.
 - Também pode se usar o comando **php artisan make:controller NomeDaPasta\\NomeDoController**, que ele já cria com todas as configurações feita acima.
 - **php artisan make:controller NomeDoController --resource**, para criar um controller com os metodos de crud.
 - Pode usar a rota: **Route::resource('/produtos', 'NomeDoController')** e a rota já irá identificar que tipo de requisição será feita e executará o método correto.
