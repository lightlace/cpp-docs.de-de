---
title: -MANIFESTUAC (bettet UAC-Informationen in Manifest) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.UACUIAccess
- VC.Project.VCLinkerTool.UACExecutionLevel
- VC.Project.VCLinkerTool.EnableUAC
dev_langs:
- C++
helpviewer_keywords:
- /MANIFESTUAC linker option
- MANIFESTUAC linker option
- -MANIFESTUAC linker option
ms.assetid: 2d243c39-fa13-493c-b56f-d0d972a1603a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bdfd872b43fbabdb14457ca54e6c4dfbe039313f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="manifestuac-embeds-uac-information-in-manifest"></a>/MANIFESTUAC (bettet UAC-Informationen in Manifest ein)
Gibt an, ob Informationen zur Benutzerkontensteuerung (UAC) in das Programmmanifest eingebettet werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
/MANIFESTUAC  
/MANIFESTUAC:NO  
/MANIFESTUAC:fragment  
/MANIFESTUAC:level=_level  
/MANIFESTUAC:uiAccess=_uiAccess  
```  
  
#### <a name="parameters"></a>Parameter  
 `fragment`  
 Eine Zeichenfolge, die den `level`-Wert und den `uiAccess`-Wert enthält. Weitere Informationen finden Sie unter "Hinweise" weiter unten in diesem Thema.  
  
 `_level`  
 Einer der *AsInvoker*, *HighestAvailable*, oder *RequireAdministrator*. Wird standardmäßig auf "asInvoker" festgelegt. Weitere Informationen finden Sie unter "Hinweise" weiter unten in diesem Thema.  
  
 `_uiAccess`  
 `true`, wenn die Anwendung Sicherheitsebenen für Benutzeroberflächen umgehen und Eingabe in Fenster mit höheren Berechtigungen auf dem Desktop lenken soll; andernfalls `false`. Wird standardmäßig auf `false` festgelegt. Nur für barrierefreie Anwendungen mit Benutzeroberflächen auf `true` festlegen.  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie mehrere /MANIFESTUAC-Optionen in der Befehlszeile eingeben, erhält die zuletzt eingegebene den Vorrang.  
  
 Für "/MANIFESTUAC:level" gibt es folgende Auswahlmöglichkeiten:  
  
-   `asInvoker`: Die Anwendung wird mit den gleichen Berechtigungen wie der Prozess ausgeführt, der sie gestartet hat. Die Anwendung kann auf eine höhere Berechtigungsebene erweitert werden, dazu **als Administrator ausführen**.  
  
-   "highestAvailable": Die Anwendung wird auf der höchsten für sie verfügbaren Berechtigungsebene ausgeführt. Wenn der Benutzer, der die Anwendung startet, Mitglied der Gruppe "Administratoren" ist, entspricht diese Option "requireAdministrator". Wenn die höchste verfügbare Berechtigungsebene höher als die Ebene des öffnenden Prozesses ist, fordert das System zur Eingabe von Anmeldeinformationen auf.  
  
-   "requireAdministrator": Die Anwendung wird mit Administratorrechten ausgeführt. Der Benutzer, der die Anwendung startet, muss ein Mitglied der Gruppe "Administratoren" sein. Wenn der öffnende Prozess nicht mit Administratorrechten ausgeführt wird, fordert das System zur Eingabe von Anmeldeinformationen auf.  
  
 Sie können die Ebene und die uiAccess-Werte in einem Schritt angeben, indem Sie die /MANIFESTUAC:fragment-Option verwenden. Das Fragment muss das folgende Format aufweisen:  
  
```  
"level=[ asInvoker | highestAvailable | requireAdministrator ] uiAccess=[ true | false ]"  
```  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Erweitern Sie die **Konfigurationseigenschaften** Knoten.  
  
3.  Erweitern Sie die **Linker** Knoten.  
  
4.  Wählen Sie die **Manifestdatei** Eigenschaftenseite.  
  
5.  Ändern der **Benutzerkontensteuerung aktivieren (UAC)**, **UAC-Ausführungsebene**, und **Schutz vor umgehen der Benutzeroberfläche für die Benutzerkontensteuerung** Eigenschaften.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EnableUAC%2A>, <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.UACExecutionLevel%2A> und <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.UACUIAccess%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)