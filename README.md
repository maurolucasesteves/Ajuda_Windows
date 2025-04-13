# Gerenciador de Segurança do Windows 11
Visão Geral
O Gerenciador de Segurança do Windows é uma ferramenta em PowerShell desenvolvida para auxiliar na administração e controle das configurações de segurança do Windows 11. Esta ferramenta permite verificar, ativar e desativar diversos componentes de segurança do sistema operacional, além de conceder permissões administrativas avançadas quando necessário.
Recursos Principais

Verificação do status atual das configurações de segurança
Ativação/desativação do Windows Defender
Ativação/desativação do UAC (Controle de Conta de Usuário)
Concessão de permissões administrativas avançadas
Restauração das configurações padrão de segurança

Requisitos

Windows 11
PowerShell 5.1 ou superior
Privilégios de administrador para execução

Instalação

Faça o download do arquivo WindowsSecurityManager.ps1
Salve-o em uma localização de fácil acesso no seu computador
Se necessário, desbloqueie o arquivo:

Clique com o botão direito no arquivo
Selecione "Propriedades"
Na aba "Geral", marque a opção "Desbloquear" (se disponível)
Clique em "OK"



Como Usar

Abra o PowerShell como administrador:

Clique com o botão direito no menu Iniciar
Selecione "Windows PowerShell (Admin)" ou "Terminal (Admin)"


Navegue até o diretório onde salvou o script:
powershellcd C:\Caminho\Para\O\Script

Execute o script:
powershell.\WindowsSecurityManager.ps1

Se o script não for iniciado com privilégios de administrador, ele tentará se elevar automaticamente.
Utilize o menu interativo para navegar pelas diferentes opções.

Funções Detalhadas
1. Verificar Status Atual
Esta função exibe o estado atual de:

Windows Defender (proteção em tempo real)
UAC (Controle de Conta de Usuário) e seu nível de configuração
Firewall do Windows para todos os perfis (Domínio, Privado, Público)
SmartScreen do Windows

2. Desativar Windows Defender
Desativa a proteção em tempo real e outros componentes do Windows Defender:

Monitoramento em tempo real
Monitoramento de comportamento
Proteção contra ameaças na nuvem
Proteção contra ameaças baseadas em IO
Verificação de scripts

3. Ativar Windows Defender
Reativa todos os componentes do Windows Defender que foram desativados.
4. Desativar UAC
Desativa o Controle de Conta de Usuário, eliminando as solicitações de confirmação ao executar tarefas administrativas.
5. Ativar UAC
Reativa o Controle de Conta de Usuário com as configurações padrão de segurança.
6. Conceder Permissões Totais de Administrador
Aplica várias configurações para maximizar os privilégios administrativos:

Garante que o usuário atual seja membro do grupo Administradores
Configura o UAC para o nível mínimo
Desativa restrições de execução para arquivos executáveis
Configura política de execução irrestrita para o PowerShell
Desativa o SmartScreen do Windows
Desativa a proteção em tempo real do Windows Defender

7. Restaurar Configurações Padrão
Reverte todas as alterações de segurança para os valores padrão do Windows, reativando:

UAC com nível padrão
Windows Defender e todos os seus componentes
SmartScreen do Windows
Política de execução padrão do PowerShell
Firewall do Windows para todos os perfis

Notas de Segurança
⚠️ ATENÇÃO:

Este script modifica configurações críticas de segurança do Windows
Desabilitar os recursos de segurança pode deixar seu sistema vulnerável a malware, ransomware e outras ameaças
Use este script com cautela e apenas quando realmente necessário
Recomenda-se restaurar as configurações padrão após concluir as tarefas administrativas
Muitas alterações requerem reinicialização do sistema para efeito completo

Propósito Educacional
Esta ferramenta foi desenvolvida para fins educacionais, permitindo compreender:

Como o Windows 11 implementa suas camadas de segurança
Como as configurações de segurança podem ser gerenciadas programaticamente via PowerShell
O impacto das diferentes configurações de segurança no sistema operacional

Solução de Problemas

Se o script não executar, verifique a política de execução do PowerShell:
powershellGet-ExecutionPolicy
Se necessário, altere temporariamente para permitir a execução:
powershellSet-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass

Algumas configurações podem ser bloqueadas por políticas organizacionais ou pelo Windows Defender Credential Guard/Device Guard.
Para determinar por que uma configuração específica não pôde ser alterada, verifique o Event Viewer para mensagens de erro relacionadas.

Limitações

Algumas configurações de segurança avançadas no Windows 11 podem não ser facilmente alteráveis, mesmo com privilégios administrativos
Alterações em certas configurações podem ser revertidas automaticamente pelo sistema em atualizações ou verificações de segurança
Este script não modifica configurações que exigem alterações do modo de inicialização segura ou UEFI


Desenvolvido para fins educacionais e administrativos.
Última atualização: Abril 2025
