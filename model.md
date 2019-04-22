# Model
-   **php artisan make:model Tabela -m**.
-   Sempre colocar o nome do model no singular e o **-m** é para criar a migration.
-   Se caso eu for organizar as models dentro de pastas ao rodar o comando de criação do model passar *nomeDaPasta\\\nomeDoModel*.
-   Caso o nome da sua tabela no banco de dados nao esteja no plural ou até mesmo por outro motivo, adicione a seguinte propriedade na model: 

	> protected $table = 'NomeDaTabela';

-   No controller relacionado a model criada, dar um **USE** onde o model estiver, no método que será usado algo do banco de dados, passar como parametro da seguinte forma **function meuMetodo(NomeDoModel  $ NomeDoModel)** e assim você consegue já fazer algumas coisas com essa tabela, exemplo, lista tudo: **$NomeDoModel->all();**, também posso instanciar o model num construtor para servir para todos os metodos. 
-   Usar o metodo **create** para inserir algum registro no banco, porém preciso definir na model quais campos pode ser preenchido quando se é passado um array.  
-   Criar a propriedade *protected* com o nome **$fillable** e passar o array dos campos que pode ser preenchido ou criar a **$guarded** e passar os campos que não podem ser preenchidos.  
    
  ### FAZER SELECT  
  > Table->all();
  
  > Table::select('name','surname')->where('id', 1)->get();
  
  > ModelName::find($id, ['name', 'surname']); *Segundo parametro é as colunas que irão aparecer*
  

  ### FAZER UM UPDATE

-   Usa o método para retornar as informações do registro que você quer alterar:  
    > $teste = $this->product->find(5); - *esse metodo find retorna as informações do id passado como parametro.*
    
-   Agora posso usar o método update: 
	>$teste->update(['Aqui terá um array']); - *e o metodo update ele retorna true ou false.*  
    
-   Posso usar da seguinte forma também: 
	>$teste = $this->product->find(5)->update(['aqui tera um array']);  
	
-   Caso o update nao for pelo *ID*, pode trocar o metodo **find** pelo **where('nomeDoCampo', ' <> *opcional*', 'Valor de comparação');**

-   Segue abaixo um exemplo de update:

	> public function update(Request $request){
	>
	> $produto = Produtos::find($request->id);
	>
	>$produto->fill($request->all());
	>	
	>$produto->save();
	>
	>return response()->json($produto); *Esse retorno é usado em caso de API*
	>
	>}
    
  ### FAZER UM DELETE  

-   Mesma ideia do update,  **$this->product->find(5)->delete();**  
-   Ou posso usar o seguinte método: **$this->product->destroy(5);**
-   O interessante do destroy é que posso passar um array como parâmetro;  
-   A ideia do **where** funciona da mesma forma que no update.
