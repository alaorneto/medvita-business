# Arquitetura

Medvita Business é um repositório com várias apps do Skeleton. Cada app é um pacote publicado sozinho (`.skapp`), contratado sozinho e ativado por organização; todas andam num só trem de versão.

## Lugar na suíte

```text
add-ons de especialidade
        ▲
Medvita Business   (clínica, pessoa jurídica)
        ▲
Medvita Pro        (avançado)
        ▲
medvita-core       (pacientes, agenda, prontuário, financeiro)
        ▲
Skeleton           (núcleo)
```

A seta aponta para quem se instala por cima. Uma camada usa a de baixo pelo `service_api`, pelos eventos de domínio e pelos registries (`docs/extension-points.md` do medvita-core); a de baixo nunca conhece a de cima.

## Árvore do repositório

```text
medvita-business/                <- raiz do repositório git; não é pacote Python
  AGENTS.md  LICENSE  README.md  pyproject.toml
  .github/             <- dev-workflow, CI, modelos de issue e PR
  .claude/skills/dev-workflow/
  docs/                <- documentação do pacote
  tools/  tests/       <- chegam com o epic de bootstrap
  med_<nome>/          <- uma app por diretório, no formato das apps do medvita-core
```

## Apps planejadas

| Pacote e label | `app_id` | Nome exibido | Depende de |
|---|---|---|---|
| `med_nfse` | `io.medvita.nfse` | NFS-e | Financeiro, Assinatura digital (Pro) |
| `med_telehealth` | `io.medvita.telehealth` | Telemedicina | Agenda médica, Prontuário, Prescrição (Pro) |
| `med_insights` | `io.medvita.insights` | Indicadores | Agenda médica, Financeiro |
| `med_inventory` | `io.medvita.inventory` | Estoque | Prontuário, Financeiro |
| `med_interop` | `io.medvita.interop` | Interoperabilidade | Pacientes, Prontuário |

Cada dependência é declarada em `dependencies` do manifesto da app, com a faixa da versão instalada.
