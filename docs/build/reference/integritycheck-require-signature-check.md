---
title: /INTEGRITYCHECK (Signaturprüfung erforderlich)
ms.date: 11/04/2016
ms.assetid: 9e738825-2c98-40cd-8ad2-5d0d9c14893e
ms.openlocfilehash: a46f31140c01753fdaa6e72fd0f741f569a5ad94
ms.sourcegitcommit: 28eae422049ac3381c6b1206664455dbb56cbfb6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2019
ms.locfileid: "66450442"
---
# <a name="integritycheck-require-signature-check"></a>/INTEGRITYCHECK (Signaturprüfung erforderlich)

Gibt an, dass die digitale Signatur des Binärimages zur Ladezeit überprüft werden muss.

```
/INTEGRITYCHECK[:NO]
```

## <a name="remarks"></a>Hinweise

In der Standardeinstellung **/INTEGRITYCHECK** ist deaktiviert.

Die **/INTEGRITYCHECK** Optionssätze – im PE-Header der ausführbaren Datei oder DLL-Datei – ein Flag für die Speicher-Manager, die für eine digitale Signatur überprüft werden soll, um das Image in Windows zu laden. Diese Option muss für 32-Bit- und 64-Bit-DLLs, die von bestimmten Windows-Funktionen geladen Kernelmoduscode implementieren festgelegt werden, und es wird empfohlen, für alle Gerätetreiber unter Windows Vista, Windows 7, Windows 8, Windows Server 2008 und Windows Server 2012. Windows-Versionen vor Windows Vista ignorieren dieses Flag. Weitere Informationen finden Sie unter [erzwungene Integritätssignierung von Portable ausführbare Datei (Dateien, PE)](https://social.technet.microsoft.com/wiki/contents/articles/255.forced-integrity-signing-of-portable-executable-pe-files.aspx).

### <a name="to-set-this-linker-option-in-visual-studio"></a>So legen Sie diese Linkeroption in Visual Studio fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen erhalten Sie unter [Set C++ compiler and build properties in Visual Studio (Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio)](../working-with-project-properties.md).

1. Erweitern Sie den Knoten **Konfigurationseigenschaften**.

1. Erweitern Sie den Knoten **Linker**.

1. Wählen Sie die **Befehlszeile** Eigenschaftenseite.

1. In **zusätzliche Optionen**, geben Sie `/INTEGRITYCHECK` oder `/INTEGRITYCHECK:NO`.

## <a name="see-also"></a>Siehe auch

[MSVC-Linkerreferenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)<br/>
[Erzwungene Integrität Signieren der portierbare ausführbare Datei (PE)-Dateien](https://social.technet.microsoft.com/wiki/contents/articles/255.forced-integrity-signing-of-portable-executable-pe-files.aspx)<br/>
[Exemplarische Vorgehensweise für Kernelmodus-Codesignatur](https://msdn.microsoft.com/windows/hardware/gg487328.aspx)<br/>
[AppInit-DLLs in Windows 7 und WindowsServer 2008](https://msdn.microsoft.com/windows/hardware/gg463040.aspx)
