---
title: /ERRORREPORT (Weiterleiten von internen Linkerfehlern)
ms.date: 12/28/2017
f1_keywords:
- /ERRORREPORT
- VC.Project.VCLinkerTool.ErrorReporting
helpviewer_keywords:
- /ERRORREPORT linker option
- ERRORREPORT linker option
- -ERRORREPORT linker option
ms.assetid: f5fab595-a2f1-4eb0-ab5c-1c0fbd3d8c28
ms.openlocfilehash: 26cc157cb7247a3a2ea7c10b415df1160540c9ad
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57818023"
---
# <a name="errorreport-report-internal-linker-errors"></a>/ERRORREPORT (Weiterleiten von internen Linkerfehlern)

> **/ errorreport:**[ **keine** | **Eingabeaufforderung** | **Warteschlange** | **senden** ]

## <a name="arguments"></a>Argumente

**none**<br/>
Berichte zu internen Compilerfehlern werden nicht gesammelt oder an Microsoft gesendet.

**Aufforderung**<br/>
Sie werden aufgefordert, einen Bericht zu senden, wenn Sie einen internen Compilerfehler empfangen. **Eingabeaufforderung** ist die Standardeinstellung, bei der Kompilierung einer Anwendung in der Entwicklungsumgebung.

**Warteschlange**<br/>
Der Fehlerbericht wird in die Warteschlange gesetzt. Wenn Sie sich mit Administratorberechtigungen anmelden, wird ein Fenster angezeigt, sodass Sie alle Fehler seit dem letzten melden können, Sie wurden angemeldet (nicht werden Sie aufgefordert, Fehlerberichte mehr als einmal alle drei Tage zu senden). **Warteschlange** ist die Standardeinstellung, wenn eine Anwendung an der Befehlszeile kompiliert wird.

**Senden**<br/>
Sendet automatisch Berichte über interne Compilerfehler an Microsoft, wenn die berichterstellung durch die Windows Error Reporting Service-Einstellungen aktiviert ist.

## <a name="remarks"></a>Hinweise

Die **/errorreport** Option können Sie die Informationen interne Compilerfehler (ICE) direkt an Microsoft zu senden.

Die Option **/errorreport: Send** Fehlerinformationen automatisch an Microsoft sendet, wenn von Windows Error Reporting Service-Einstellungen aktiviert.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Öffnen der **Konfigurationseigenschaften** > **Linker** > **erweitert** Eigenschaftenseite.

1. Ändern der **Fehlerberichterstattung** Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ErrorReporting%2A>.

## <a name="see-also"></a>Siehe auch

[/errorReport (Interne Compilerfehler melden)](errorreport-report-internal-compiler-errors.md)<br/>
[MSVC-Linker-Referenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)
