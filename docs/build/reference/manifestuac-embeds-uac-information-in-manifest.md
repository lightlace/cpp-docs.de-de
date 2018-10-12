---
title: -MANIFESTUAC (bettet UAC-Informationen in Manifest) | Microsoft-Dokumentation
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
ms.openlocfilehash: d8c8c3cc219f0cf658dc2669ccc10adf3aba55bd
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2018
ms.locfileid: "49163529"
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

### <a name="parameters"></a>Parameter

*Fragment*<br/>
Eine Zeichenfolge, die den `level`-Wert und den `uiAccess`-Wert enthält. Weitere Informationen finden Sie unter "Hinweise" weiter unten in diesem Thema.

*_level*<br/>
Einer der *"asInvoker"*, *"highestAvailable"*, oder *"requireAdministrator"*. Wird standardmäßig auf "asInvoker" festgelegt. Weitere Informationen finden Sie unter "Hinweise" weiter unten in diesem Thema.

*_uiAccess*<br/>
**"true"** sollten Sie die Anwendung Sicherheitsebenen für Benutzeroberflächen umgehen und das Laufwerk input mit höheren Berechtigungen von Windows auf dem Desktop; andernfalls **"false"**. Standardmäßig **"false"**. Legen Sie auf **"true"** nur für barrierefreiheitsanwendungen mit Benutzeroberflächen.

## <a name="remarks"></a>Hinweise

Wenn Sie mehrere /MANIFESTUAC-Optionen in der Befehlszeile eingeben, erhält die zuletzt eingegebene den Vorrang.

Für "/MANIFESTUAC:level" gibt es folgende Auswahlmöglichkeiten:

- `asInvoker`: Die Anwendung wird mit den gleichen Berechtigungen wie der Prozess ausgeführt, der sie gestartet hat. Die Anwendung auf eine höhere Berechtigung erweitert werden kann, dazu **als Administrator ausführen**.

- "highestAvailable": Die Anwendung wird auf der höchsten für sie verfügbaren Berechtigungsebene ausgeführt. Wenn der Benutzer, der die Anwendung startet, Mitglied der Gruppe "Administratoren" ist, entspricht diese Option "requireAdministrator". Wenn die höchste verfügbare Berechtigungsebene höher als die Ebene des öffnenden Prozesses ist, fordert das System zur Eingabe von Anmeldeinformationen auf.

- "requireAdministrator": Die Anwendung wird mit Administratorrechten ausgeführt. Der Benutzer, der die Anwendung startet, muss ein Mitglied der Gruppe "Administratoren" sein. Wenn der öffnende Prozess nicht mit Administratorrechten ausgeführt wird, fordert das System zur Eingabe von Anmeldeinformationen auf.

Sie können die Ebene und die uiAccess-Werte in einem Schritt angeben, indem Sie die /MANIFESTUAC:fragment-Option verwenden. Das Fragment muss das folgende Format aufweisen:

```
"level=[ asInvoker | highestAvailable | requireAdministrator ] uiAccess=[ true | false ]"
```

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Erweitern Sie den Knoten **Konfigurationseigenschaften**.

1. Erweitern Sie die **Linker** Knoten.

1. Wählen Sie die **Manifestdatei** Eigenschaftenseite.

1. Ändern der **aktivieren User Account Control (UAC)**, **UAC-Ausführungsebene**, und **Schutz vor umgehen der Benutzeroberfläche für die Benutzerkontensteuerung** Eigenschaften.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

1. Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EnableUAC%2A>, <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.UACExecutionLevel%2A> und <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.UACUIAccess%2A>.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)