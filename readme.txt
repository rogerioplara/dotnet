dotnet CLI -> command line interface

dotnet --list-sdks -> lista as sdks instaladas no sistema

dotnet --list-runtimes -> lista as runtimes instaladas
 
dotnet help -> ajuda

Tipos de projeto {
    - Class library {
        resultado final é uma DLL
        não possui interface
    }
    - Console application {
        resultado final é uma aplicação que roda no terminal
        pode receber dados, esperar input do usuário
    }
    - Projeto web {
        ASP.NET web
        ASP.NET mvc
        ASP.NET webapi
    }
    - Projeto testes {
        microsoft tests
    }
}

Criando um novo projeto {
    - dotnet cli {
        dotnet new console -> novo console application
        dotnet new classlib -> nova class library
        dotnet new web -> novo projeto ASP.NET core
        dotnet new mvc -> novo projeto ASP.NET core
        dotnet new webapi -> novo projeto ASP.NET core
        dotnet new mstest -> novo projeto microsoft test
    }
    - definições {
        criar um projeto é o mesmo que gerar os arquivos iniciais de uma aplicação;
        sempre vai gerar os arquivos na pasta atual
        para especificar uma pasta, utilizar ex:'dotnet new console -o NomeDoApp';
        aplicações do dotnet tendem a iniciar sempre com a inicial maiúscula;
        um projeto dotnet sempre terá um arquivo com a extensão .csproj;
    }
}

Debug {
    - Obrigatóriamente será feito em um arquivo .cs;
}

Executando a apliação {
    - dotnet restore {
        restaura todos os pacotes que a aplicação precisa para executar e fazer a instalação deles;
        recomendado executar sempre que abrir um novo projeto;
    }
    - dotnet build {
        compilar a aplicação;
        vai gerar avisos e erros se houver;
    }
    - dotnet clean {
        limpa o cache de memória das aplicações;
        recomendado a fazer sempre antes de executar um build para evitar sujeira na aplicação;
    }
    - dotnet run {
        executa a aplicação de fato;
        variáveis de ambiente {
            aplicações possuem vários ambientes e cada um possui suas configurações, é possível ter n ambientes; 
            - desenvolvimento
            - homologação
            - produção
            é possível dizer ao .net qual ambiente estamos utilizando {
                dotnet run --environment=seu_ambiente
                dotnet run --environment=development
                dotnet run --environment=production
            }
        }
    }
}

Estrutura de um console app [
    - Arquivo .csproj {
        formato xml;
        definições do projeto;
        presente em todo projeto .net;
    }
    - Program.cs {
        arquivo principal (C#);
        porta de entrada;
        será o primeiro a ser executado;
    }
]

Escopo de um programa {
    - Importações {
        Ficam no começo do arquivo;
        Sempre definidas pelo using;
        Definem as bibliotecas que nosso programa irá utilizar;
        Por padrão só o básico vem incluso;
        Precisamos importar o que desejamos para poder trabalhar;
    }
    - Namespace {
        Divisão lógica dentro da aplicação (divisão física é feita pelos arquivos);
        Não podemos ter duas classes com o mesmo nome em um namespace;
        O ideal é ter apenas um namespace e uma classe por arquivo;
        Namespaces podem ser reutilizados em diversos arquivos;
        Não existe limite de quantidade nos namespaces;
        Não devem conter espaços ou caracteres especiais;
        Toda palavra no namespace começa com maiúsculo;
        Podemos ter um namespace dentro de outro utilizando o '.' para concatenar ex: MeuApp.Teste;
        Durante a execução, todos os arquivos do c# são unificados;
        A divisão física se perderá, ficando apenas a divisão lógica, os namespaces;
    }
    - Classe {}
    - Método principal (Main) {}
}

Built-in types {
    Tipos primitivos;
    Tipos base cujo outros tipos (complexos) vão derivar;
    Definir o tipo correto otimiza a execução do programa;
    São chamados de tipos de valor;
    Classificados em {
        Tipos simples (simple types);
        Enumeradores (enums);
        Estruturas (structs);
        Tipos nulos (nullable types);
    }
}

System {
    No .net tudo começa de um tipo base chamado System;
    Todo e qualquer tipo, seja build-in ou complexo deriva dele;
    Base de todos os objetos no .net;
    Seu uso já é implícito;
}