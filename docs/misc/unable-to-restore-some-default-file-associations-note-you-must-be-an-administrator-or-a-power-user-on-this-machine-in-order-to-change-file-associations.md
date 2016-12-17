---
title: "Einige Standarddateizuordnungen k&#246;nnen nicht wiederhergestellt werden. Hinweis: Sie m&#252;ssen auf diesem Computer Administrator oder Poweruser sein, um Dateizuordnungen zu &#228;ndern."
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "VS.Message.0x00006A85"
  - "VS_E_RESTOREFILEASSOCS"
ms.assetid: 449c5608-83e3-4ddd-91f1-1061916995b3
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "douge"
---
# Einige Standarddateizuordnungen k&#246;nnen nicht wiederhergestellt werden. Hinweis: Sie m&#252;ssen auf diesem Computer Administrator oder Poweruser sein, um Dateizuordnungen zu &#228;ndern.
Dieser Fehler tritt auf, wenn der Befehlszeilenschalter „\/AssociateFiles“ des Befehls „devenv“ verwendet wird, die aktuellen Benutzerrechte aber keinen Zugriff auf den Abschnitt HKEY\_CLASSES\_ROOT der Registrierung gestatten. Wenn Sie [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] auf [!INCLUDE[wiprlhext](../c-runtime-library/reference/includes/wiprlhext_md.md)] ausführen, müssen Sie „devenv“ als Administrator ausführen, um den Schalter „\/AssociateFiles“ \(devenv.exe\) zu verwenden.  
  
### So beheben Sie diesen Fehler  
  
-   Wechseln Sie zu Administratoranmeldeinformationen, und versuchen Sie es noch einmal.  
  
## Siehe auch  
 [User Rights and Visual Studio](assetId:///d5c55084-1e7b-4b61-b478-137db01c0fc0)   
 [Devenv\-Befehlszeilenschalter](../Topic/Devenv%20Command%20Line%20Switches.md)