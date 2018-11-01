---
title: /errorReport (Meldung über interne Compilerfehler)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.ErrorReporting
- /errorreport
helpviewer_keywords:
- /errorReport compiler option [C++]
- -errorReport compiler option [C++]
ms.assetid: 819828f8-b0a5-412c-9c57-bf822f17e667
ms.openlocfilehash: 8529e8c3cfc0914797c81207889a9505f1d57382
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50660160"
---
# <a name="errorreport-report-internal-compiler-errors"></a>/errorReport (Meldung über interne Compilerfehler)

Ermöglicht es Ihnen, Informationen über interne Compilerfehler (ICE) direkt an Microsoft zu senden.

## <a name="syntax"></a>Syntax

```
/errorReport:[ none | prompt | queue | send ]
```

## <a name="arguments"></a>Argumente

**none**<br/>
Berichte zu internen Compilerfehlern werden nicht gesammelt oder an Microsoft gesendet.

**Aufforderung**<br/>
Sie werden aufgefordert, einen Bericht zu senden, wenn Sie einen internen Compilerfehler empfangen. **Eingabeaufforderung** ist die Standardeinstellung, bei der Kompilierung einer Anwendung in der Entwicklungsumgebung.

**Warteschlange**<br/>
Der Fehlerbericht wird in die Warteschlange gesetzt. Wenn Sie sich mit Administratorberechtigungen anmelden, wird ein Fenster angezeigt, sodass Sie alle Fehler seit dem letzten melden können, Sie wurden angemeldet (nicht werden Sie aufgefordert, Fehlerberichte mehr als einmal alle drei Tage zu senden). **Warteschlange** ist die Standardeinstellung, wenn eine Anwendung an der Befehlszeile kompiliert wird.

**Senden**<br/>
Sendet automatisch Berichte über interne Compilerfehler an Microsoft, wenn die berichterstellung durch die Einstellungen für das Windows-Fehlerberichterstattung aktiviert ist.

## <a name="remarks"></a>Hinweise

Ein interner Compilerfehler (ICE) entsteht, wenn der Compiler eine Quellcodedatei nicht verarbeiten kann. Tritt ein ICE auf, erzeugt der Compiler keine Ausgabedatei oder eine hilfreiche Diagnose, die Sie verwenden können, um Ihren Code zu beheben.

In früheren Versionen wurden Sie, wenn Sie eine Compilerfehlers aufgefordert, rufen Sie den Microsoft Support Services, um das Problem zu melden. Mit **/errorreport**, Sie können die ICE-Informationen bereitstellen, direkt an Microsoft. Die Fehlerberichte können dabei helfen, zukünftige Compilerversionen zu verbessern.

Die Fähigkeit eines Benutzers zum Senden von Berichten hängt vom Computer und den Benutzerberechtigungen ab.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Klicken Sie auf den Ordner **C/C++** .

1. Klicken Sie auf die **erweitert** Eigenschaftenseite.

1. Ändern der **Fehlerberichterstattung** Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ErrorReporting%2A>.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)