# 📩 N8N to GitHub Auto-Backup

## 📌 Descrição  
Workflow do N8N que automatiza o backup periódico de todos os seus fluxos de trabalho diretamente para um repositório no GitHub. Garante segurança, versionamento e capacidade de rollback dos seus processos automatizados.

### Funcionalidades principais:  
- ✅ Backup automático em intervalos regulares (via Schedule Trigger)
- ✅ Versionamento completo com histórico de alterações no GitHub
- ✅ Upload inteligente - verifica e atualiza apenas arquivos modificados
- ✅ Estrutura organizada com arquivos JSON individuais para cada workflow
- ✅ Nomenclatura automática de arquivos (nome-workflow-id.json)
- ✅ Commit messages com timestamp para rastreabilidade
- ✅ Processamento em lote (batch size: 1) para maior confiabilidade

## 🛠️ Tecnologias utilizadas  
- **N8N** - Plataforma de automação de workflows
- **GitHub API** - Integração com repositórios Git via OAuth2
- **N8N API** - Comunicação com a instância N8N local
- **JSON/Binary Data** - Manipulação e transformação de dados

## ⚙️ Estrutura do Workflow  
1. **Schedule Trigger** - Inicia o processo automaticamente (configurável por horas)
2. **Set & Format Date** - Prepara timestamp no formato `dd-MM-yyyy/H:mm` para commits
3. **List Files from Repository** - Obtém lista de arquivos existentes no GitHub
4. **Combine File Names** - Agrega nomes para verificação em lote
5. **Retrieve Workflows [N8N]** - Obtém todos os workflows da instância N8N
6. **Move JSON to Binary** - Converte e nomeia arquivos para backup
7. **Split to Single Items** - Processa workflows individualmente
8. **Check if File Exists** - Verifica se o arquivo já existe no repositório
9. **Update/Create File** - Upload inteligente no GitHub baseado na verificação

## 📷 Captura do Workflow  
![AUTOBACKUP](https://github.com/user-attachments/assets/b33458ee-7cb4-4268-b1ad-c925d7fde82b)

## 🚀 Como usar  
1. **Importe o JSON** do workflow para sua instância N8N
2. **Configure as credenciais**:
   - `GitHub OAuth2` - Para acesso ao repositório
   - `N8N API` - Para comunicação com sua instância
3. **Ajuste as configurações**:
   - Owner e Repository no GitHub
   - Schedule de execução (horas, dias, etc.)
   - Formato de data se necessário
4. **Ative o workflow** - Os backups começarão automaticamente

**Configurações atuais:**
- Repositório: `HeytorAlves/N8N-WORKFLOWS-BACKUP`
- Formato arquivos: `nome-workflow-id.json`
- Schedule: Horas (configurável)

## 📌 Autor  
Desenvolvido por **HeytorAlves**

---

**Nota:** Este workflow cria um sistema completo de backup com versionamento, permitindo recuperação pontual de qualquer versão dos seus workflows através do histórico do Git.
