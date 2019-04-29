---
title: /TSAWARE (Terminalserverfähige Anwendung erstellen)
ms.date: 11/04/2016
f1_keywords:
- /tsaware
- VC.Project.VCLinkerTool.TerminalServerAware
helpviewer_keywords:
- Terminal Server
- /TSAWARE linker option
- Terminal Server, Terminal Server-aware applications
- -TSAWARE linker option
- TSAWARE linker option
ms.assetid: fe1c1846-de5b-4839-b562-93fbfe36cd29
ms.openlocfilehash: f6ed6184f8ae4b3a0f9db3c1f962a2918a185138
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62317431"
---
# <a name="tsaware-create-terminal-server-aware-application"></a>/TSAWARE (Terminalserverfähige Anwendung erstellen)

```
/TSAWARE[:NO]
```

## <a name="remarks"></a>Hinweise

Die/TSAWARE-Option legt ein Flag in das Feld IMAGE_OPTIONAL_HEADER DllCharacteristics im optionalen Header des Programm-Images. Wenn dieses Flag festgelegt ist, wird der Terminalserver keine bestimmten Änderungen an der Anwendung vornehmen.

Wenn eine Anwendung nicht Terminal Server kennen (auch bekannt als eine ältere Anwendung) ist, macht Terminalserver bestimmte Änderungen an die ältere Anwendung nicht ordnungsgemäß in einer mehrbenutzerumgebung machen. Terminal Server wird z. B. einen virtuellen Windows-Ordner erstellt, so, dass jeder Benutzer einen Windows-Ordner anstelle der Windows Systemverzeichnis erhält. Dies ermöglicht Benutzern den Zugriff auf ihre eigenen INI-Dateien. Darüber hinaus macht Terminal Server einige Anpassungen an der Registrierung für eine ältere Anwendung. Diese Änderungen verlangsamt das Laden von die ältere Anwendung auf dem Terminalserver.

Wenn eine Anwendung Terminal Server kompatibel ist, es sind weder INI-Dateien noch muss Schreiben in die **HKEY_CURRENT_USER** Registrierung während des Setups.

Wenn Sie/TSAWARE und Ihre Anwendung weiterhin INI-Dateien verwendet, werden die Dateien von allen Benutzern des Systems freigegeben werden. Wenn dies zulässig ist, können Sie weiterhin Ihre Anwendung mit/TSAWARE verknüpfen; Andernfalls müssen Sie: NO verwenden.

Die/TSAWARE-Option ist standardmäßig aktiviert, für Windows und konsolenanwendungen. Finden Sie unter [/Subsystem](subsystem-specify-subsystem.md) und [/Version](version-version-information.md) Informationen.

/ TSAWARE gilt nicht für die Treiber, VxDs oder DLLs.

Wenn eine Anwendung mit/TSAWARE, DUMPBIN verknüpft wurde [/Headers](headers.md) zeigt Informationen zu diesem Zweck an.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Klicken Sie auf die **Linker** Ordner.

1. Klicken Sie auf die **System** Eigenschaftenseite.

1. Ändern der **Terminal Server** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TerminalServerAware%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Linkerreferenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)<br/>
[Das Speichern von benutzerspezifischen Informationen](/windows/desktop/TermServ/storing-user-specific-information)<br/>
[Ältere Anwendungen in einer Terminaldienstumgebung](https://msdn.microsoft.com/library/aa382957.aspx)
