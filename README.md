# DIO - Trilha .NET - Explorando a linguagem C#

Projeto desenvolvido como desafio do módulo de Fundamentos da trilha .NET da [DIO](https://www.dio.me/).

## Desafio

Construa um sistema para gerenciar reservas em um hotel, utilizando as classes `Pessoa`, `Suíte` e `Reserva`. O sistema deve calcular corretamente o valor das diárias, aplicar descontos e validar a capacidade das suítes.

## Contexto

Você foi contratado para construir um sistema de hospedagem, que será usado para realizar reservas em um hotel. O sistema deve:

- Gerenciar hóspedes (`Pessoa`)
- Gerenciar suítes (`Suíte`)
- Gerenciar reservas (`Reserva`), relacionando hóspedes e suítes

## Regras e Validações

1. **Capacidade da Suíte:**  
   Não é permitido reservar uma suíte com capacidade menor do que a quantidade de hóspedes.  
   Exemplo: Suíte para 2 pessoas não pode ser reservada para 3 hóspedes (deve lançar uma exceção).

2. **Quantidade de Hóspedes:**  
   O método `ObterQuantidadeHospedes` da classe `Reserva` deve retornar o número total de hóspedes da reserva.

3. **Cálculo do Valor da Diária:**  
   O método `CalcularValorDiaria` deve retornar o valor total da reserva (dias reservados x valor da diária da suíte).

4. **Desconto para Longas Estadas:**  
   Reservas com 10 dias ou mais recebem 10% de desconto no valor total da diária.

## Diagrama de Classes

![Diagrama de classe hotel](diagrama_classe_hotel.png)

## Estrutura das Classes

- **Pessoa:** Representa um hóspede.
- **Suíte:** Representa uma suíte do hotel, com capacidade e valor da diária.
- **Reserva:** Relaciona hóspedes e suíte, calcula valores e valida regras.

## Como Executar

1. **Pré-requisitos:**  
   - [.NET 6.0 SDK ou superior](https://dotnet.microsoft.com/download)

2. **Clone o repositório:**
   ```bash
   git clone https://github.com/seu-usuario/seu-repositorio.git
   cd trilha-net-explorando-desafio
   ```

3. **Rode o projeto:**
   ```bash
   dotnet run
   ```

## Exemplo de Uso

```csharp
// Criando hóspedes
var hospedes = new List<Pessoa>
{
    new Pessoa("João", "Silva"),
    new Pessoa("Maria", "Oliveira")
};

// Criando suíte
var suite = new Suite("Premium", 2, 150);

// Criando reserva
var reserva = new Reserva(diasReservados: 12);
reserva.CadastrarSuite(suite);
reserva.CadastrarHospedes(hospedes);

// Exibindo informações
Console.WriteLine($"Hóspedes: {reserva.ObterQuantidadeHospedes()}");
Console.WriteLine($"Valor total: {reserva.CalcularValorDiaria()}");
```


## Licença

Este projeto é apenas para fins educacionais.
