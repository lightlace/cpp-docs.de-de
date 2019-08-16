---
title: /INTEGRITYCHECK (Signaturprüfung erforderlich)
ms.date: 11/04/2016
ms.assetid: 9e738825-2c98-40cd-8ad2-5d0d9c14893e
ms.openlocfilehash: 1732c612501b66753635b272f94764975c555f75
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492850"
---
# <a name="integritycheck-require-signature-check"></a>/INTEGRITYCHECK (Signaturprüfung erforderlich)

Gibt an, dass die digitale Signatur des Binärimages zur Ladezeit überprüft werden muss.

```
/INTEGRITYCHECK[:NO]
```

## <a name="remarks"></a>Hinweise

Standardmäßig ist **/INTEGRITYCHECK** auf OFF eingestellt.

Die Option **/INTEGRITYCHECK** legt – im PE-Header der DLL-Datei oder der ausführbaren Datei fest – ein Flag für den Speicher-Manager, um eine digitale Signatur zu überprüfen, um das Image in Windows zu laden. Diese Option muss sowohl für 32-Bit-als auch 64-Bit-DLLs festgelegt werden, die den Kernelmoduscode implementieren, der von bestimmten Windows-Funktionen geladen wird, und wird für alle Gerätetreiber unter Windows Vista, Windows 7, Windows 8, Windows Server 2008 und Windows Server 2012 empfohlen. Windows-Versionen vor Windows Vista ignorieren dieses Flag. Weitere Informationen finden Sie [unter Signierung der erzwungenen Integrität von PE-Dateien (portable ausführbare Dateien)](https://social.technet.microsoft.com/wiki/contents/articles/255.forced-integrity-signing-of-portable-executable-pe-files.aspx).

### <a name="to-set-this-linker-option-in-visual-studio"></a>So legen Sie diese Linkeroption in Visual Studio fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen des Compilers und der Buildeigenschaften](../working-with-project-properties.md).

1. Erweitern Sie den Knoten **Konfigurationseigenschaften**.

1. Erweitern Sie den Knoten **Linker**.

1. Wählen Sie die Eigenschaften Seite **Befehlszeile** aus.

1. Geben Sie `/INTEGRITYCHECK` unter **zusätzliche Optionen**oder `/INTEGRITYCHECK:NO`ein.

## <a name="see-also"></a>Siehe auch

[MSVC-Linkerreferenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)<br/>
[Erzwungene Integritäts Signatur von portablen ausführbaren Dateien (PE)](https://social.technet.microsoft.com/wiki/contents/articles/255.forced-integrity-signing-of-portable-executable-pe-files.aspx)<br/>
[Kernel Modus-Code Signierungs Anforderungen](/windows-hardware/drivers/install/kernel-mode-code-signing-requirements--windows-vista-and-later-)<br/>
[AppInit-DLLs und sicherer Start](/windows/win32/dlls/secure-boot-and-appinit-dlls)
