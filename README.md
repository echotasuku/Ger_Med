# Sistema de Gestão de Medicamentos

## Descrição
É uma plataforma em desenvolvimento que visa simplificar e aprimorar o controle de medicamentos. Este sistema oferece funcionalidades essenciais para garantir uma gestão eficiente do estoque de medicamentos, permitindo que os usuários registrem medicamentos com informações detalhadas sobre nome, descrição, quantidade em estoque, data de validade e condições de armazenamento.

O sistema organiza categorias específicas para diferentes tipos de medicamentos, gerencia fornecedores e registra as distribuições de medicamentos mediante a apresentação de receitas médicas. Além disso, o sistema alerta sobre medicamentos próximos da validade e com baixo estoque, garantindo a conformidade e eficiência na gestão dos medicamentos.

## Requisitos Funcionais

| ID   | Descrição                                                                                         | Prioridade | Dependência |
|------|---------------------------------------------------------------------------------------------------|------------|-------------|
| RF01 | O sistema permite que o farmacêutico faça o cadastro de novos medicamentos, incluindo nome, descrição, quantidade, validade, categorias, etc. | Alta       | -           |
| RF02 | O sistema permite ao farmacêutico a atualização da quantidade em estoque de medicamentos.          | Alta       | RF01        |
| RF03 | O sistema permite ao farmacêutico fazer o gerenciamento das retiradas de medicamentos, garantindo a rastreabilidade completa, incluindo data e receita médica. | Alta | RF01 |
| RF04 | O sistema permite ao farmacêutico gerar relatórios detalhados sobre o estoque, incluindo dados sobre validade e quantidade dos medicamentos. | Média | RF02 |
| RF05 | O sistema realiza a autenticação dos usuários, permitindo diferentes níveis de acesso. O farmacêutico terá acesso completo, enquanto o funcionário comum terá acesso restrito. | Alta | - |
| RF06 | O sistema permite que o farmacêutico e o administrador façam o cadastro e gerenciamento de fornecedores, incluindo informações de contato e produtos fornecidos. | Baixa | RF01 |
| RF07 | O sistema permite que o farmacêutico categorize os medicamentos, facilitando a organização e a busca de medicamentos específicos no sistema. | Média | RF01 |
| RF08 | O sistema permite que o farmacêutico controle a validade dos medicamentos, notificando-os sobre produtos próximos do vencimento. | Alta | RF01, RF02 |
| RF09 | O sistema permite que o farmacêutico e o funcionário comum anexe fotos de receitas médicas ao realizar retiradas de medicamentos, garantindo a documentação apropriada. | Média | RF03 |
| RF10 | O sistema permite que o farmacêutico e o usuário comum consultem e listem os medicamentos mais procurados por mês, utilizando uma API externa para obter esses dados. | Média | RF01 |

## Regras de Negócio

| ID   | Descrição                                                                                         |
|------|---------------------------------------------------------------------------------------------------|
| RN01 | O sistema deve estabelecer diferentes níveis de acesso para os usuários. Farmacêuticos terão acesso completo, enquanto funcionários comuns terão acesso limitado. |
| RN02 | Ao registrar a entrada ou saída de medicamentos, o sistema deve verificar se há estoque suficiente. Movimentações que resultem em estoque negativo não devem ser permitidas. |
| RN03 | Somente usuários autorizados, como os Farmacêuticos, têm permissão para modificar os medicamentos. Isso garante que alterações nos valores sejam realizadas de maneira controlada e evita ajustes não autorizados. |
| RN04 | O sistema deve monitorar a validade dos medicamentos e notificar os administradores quando um produto estiver próximo do vencimento. |
| RN05 | Todas as retiradas de medicamentos devem ser registradas, incluindo data, quantidade, junto com a receita do medicamento e o usuário responsável. |
| RN06 | Relatórios sobre o estoque atual, medicamentos próximos ao vencimento e histórico de movimentações devem ser gerados pelo sistema. |
| RN07 | O sistema deve permitir anexar fotos das receitas médicas ao registrar retiradas de medicamentos. |
| RN08 | O sistema deve manter um registro dos medicamentos mais procurados por mês e disponibilizar essa informação através de uma API externa. |

## Requisitos Não Funcionais

| ID   | Descrição                                                                                         | Categoria  | Prioridade  |
|------|---------------------------------------------------------------------------------------------------|------------|-------------|
| RNF01 | O sistema utilizará o framework Laravel para o desenvolvimento do backend.                        | Manutenibilidade / Implementação | Alta       |
| RNF02 | O sistema utilizará o framework React.js para a camada de front-end.                              | Manutenibilidade / Implementação | Alta       |
| RNF03 | O backend será implementado seguindo os princípios de uma arquitetura de API Restful para facilitar a comunicação com o frontend. | Usabilidade / Facilidade de aprendizado | Alta |
| RNF04 | O sistema deve integrar a autenticação por meio da API do Google Login para acesso ao sistema.    | Usabilidade / Segurança | Alta |
