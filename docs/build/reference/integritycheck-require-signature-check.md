---
title: -INTEGRITYCHECK (Signaturprüfung erforderlich) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
ms.assetid: 9e738825-2c98-40cd-8ad2-5d0d9c14893e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: acc43bc4175f42282014e94426717527143dc059
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43197055"
---
# <a name="integritycheck-require-signature-check"></a>/INTEGRITYCHECK (Signaturprüfung erforderlich)
Gibt an, dass die digitale Signatur des Binärimages zur Ladezeit überprüft werden muss.  
  
```  
/INTEGRITYCHECK[:NO]  
```  
  
## <a name="remarks"></a>Hinweise  
 In der Standardeinstellung **/INTEGRITYCHECK** ist deaktiviert.  
  
 Die **/INTEGRITYCHECK** Optionssätze – im PE-Header der ausführbaren Datei oder DLL-Datei – ein Flag für die Speicher-Manager, die für eine digitale Signatur überprüft werden soll, um das Image in Windows zu laden. Diese Option muss für 32-Bit- und 64-Bit-DLLs, die von bestimmten Windows-Funktionen geladen Kernelmoduscode implementieren festgelegt werden, und es wird empfohlen, für alle Gerätetreiber unter Windows Vista, Windows 7, Windows 8, Windows Server 2008 und Windows Server 2012. Windows-Versionen vor Windows Vista ignorieren dieses Flag. Weitere Informationen finden Sie unter [erzwungene Integritätssignierung von Portable ausführbare Datei (Dateien, PE)](http://social.technet.microsoft.com/wiki/contents/articles/255.forced-integrity-signing-of-portable-executable-pe-files.aspx).  
  
### <a name="to-set-this-linker-option-in-visual-studio"></a>So legen Sie diese Linkeroption in Visual Studio fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).  
  
2.  Erweitern Sie den Knoten **Konfigurationseigenschaften**.  
  
3.  Erweitern Sie die **Linker** Knoten.  
  
4.  Wählen Sie die **Befehlszeile** Eigenschaftenseite.  
  
5.  In **zusätzliche Optionen**, geben Sie `/INTEGRITYCHECK` oder `/INTEGRITYCHECK:NO`.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Optionen des Linkers](../../build/reference/linker-options.md)   
 [Erzwungene Integrität Signieren der portierbare ausführbare Datei (PE)-Dateien](http://social.technet.microsoft.com/wiki/contents/articles/255.forced-integrity-signing-of-portable-executable-pe-files.aspx)   
 [Exemplarische Vorgehensweise für Kernelmodus-Codesignatur](https://msdn.microsoft.com/windows/hardware/gg487328.aspx)   
 [AppInit-DLLs in Windows 7 und WindowsServer 2008](https://msdn.microsoft.com/windows/hardware/gg463040.aspx)