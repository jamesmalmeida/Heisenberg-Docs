# Heisenberg Docs

Manual do usuário do **Cluster Heisenberg** (Ilum – Escola de Ciência / CNPEM).

| Formato | Arquivo |
|---|---|
| Web | [heisenberg_doc.html](heisenberg_doc.html) |
| Impressão | [heisenberg_doc.pdf](heisenberg_doc.pdf) |

## Como editar

`heisenberg_doc.html` é a **fonte canônica** — edite esse arquivo. O PDF é
gerado a partir dele:

```bash
google-chrome --headless --disable-gpu --no-sandbox \
    --print-to-pdf=heisenberg_doc.pdf --no-pdf-header-footer heisenberg_doc.html
```

Antes de commitar, confira que nenhum link do índice ficou órfão:

```bash
diff <(grep -oE 'href="#[^"]+"' heisenberg_doc.html | sed 's/href="#//;s/"//' | sort -u) \
     <(grep -oE '\bid="[^"]+"' heisenberg_doc.html | sed 's/id="//;s/"//'   | sort -u)
```

O `legacy/heisenberg_doc.tex` é a versão LaTeX anterior, mantida apenas como
registro. Não é mais compilada nem publicada: manter duas fontes editadas à mão
gerou commits só para reconciliar uma com a outra, e não há engine LaTeX
instalada no cluster.

## O que o manual cobre

Acesso por SSH, tutorial de Linux para quem nunca usou terminal, transferência
de arquivos (WinSCP, scp, rsync), Environment Modules, Python com Miniconda,
Slurm de ponta a ponta (scripts, exemplos para VASP/GROMACS/Python/GPU/array,
sessão interativa, diagnóstico, memória), as regras de uso aplicadas
automaticamente pelo cluster, containers com Apptainer, boas práticas,
FAQ, cheatsheets, glossário e checklist do primeiro uso.
