# Views & Blades
No controller, você pode retornar views passando parando da seguinte forma:  

> $teste = 123;   
> $teste2 = 1543;   
> return view('nomeDaview', compact('teste', 'teste2'));

-   E na minha view posso usar essas variaveis passando: **{{ $teste }}** e **{{ $teste2 }}**.
-   Também posso usar condição **{{ $teste or 'Não existe' }}**.
-   **{!! $variavel !!}** usar dessa forma quando for executar algum código, nunca em entrada de usuário.
-   **@forelse** é interessante devido a ele funcionar igual ao foreach, porém se não existir nada no array ele retorna uma mensagem.
-   **{{-- Tag de comentario --}}**.
-   Recurso **stacker** é interessante para importar arquivos CSS ou JS.
-   Ou podemos importar usando a tag LINK ou SCRIPT e no parâmetro de importação usar **{{url('css/style.css')}}** essa é uma forma de importar.

## CRIANDO UM TEMPLATE COM BLADE

-   Criar uma view, pode ser com o nome de 'template.blade.php' e montar a estrutura básica que irá servir de template.  
-   Onde o conteúdo será dinamico, colocar um **yield('NomeParaSerUtilizado')**.
-   Na outra view onde será carregada esse template, usasse: **@extends('NomeDoArquivoTemplate')** e logo abaixo você pode já inserir o conteúdo que será dinamico usando o **@section('NomeParaSerUtilizado')** e no final colocar **@endsection**.  
-   **@include('nomeDoOutroTemplate')**, pode ser usado para importar sidebars por exemplo.
