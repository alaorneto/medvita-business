# Medvita Business

[![CI](https://github.com/alaorneto/medvita-business/actions/workflows/ci.yml/badge.svg)](https://github.com/alaorneto/medvita-business/actions/workflows/ci.yml)

Medvita Business é o pacote para clínicas (pessoa jurídica) da suíte Medvita, sobre o [Skeleton](https://github.com/alaorneto/skeleton). Ele se instala por cima do [medvita-core](https://github.com/alaorneto/medvita-core) e do [Medvita Pro](https://github.com/alaorneto/medvita-pro); cada app é publicada como um pacote `.skapp` assinado, contratada sozinha e ativada por organização.

## Apps planejadas

Nenhuma app foi implementada ainda: cada uma nasce no epic dela (veja as issues `epic`).

| Pacote e label | `app_id` | Nome exibido | Para quê |
|---|---|---|---|
| `med_nfse` | `io.medvita.nfse` | NFS-e | Nota fiscal de serviço eletrônica no padrão nacional |
| `med_telehealth` | `io.medvita.telehealth` | Telemedicina | Teleconsulta conforme a Resolução CFM 2.314/2022 |
| `med_insights` | `io.medvita.insights` | Indicadores | Indicadores de gestão a partir dos eventos das apps |
| `med_inventory` | `io.medvita.inventory` | Estoque | Materiais, medicamentos e vacinas com lote e validade |
| `med_interop` | `io.medvita.interop` | Interoperabilidade | RNDS, exportação FHIR e resultados de laboratório |

O núcleo e as apps do medvita-core não são copiados para cá: entram no ambiente como dependências instaladas.

## Como desenvolver

As regras para agentes e desenvolvedores estão no `AGENTS.md`; a arquitetura em `docs/architecture.md`. O guia de ambiente e testes (`docs/development.md`) chega com o epic de bootstrap.

## Licença

Software proprietário da Katuá Tech. Todos os direitos reservados; veja `LICENSE`.
