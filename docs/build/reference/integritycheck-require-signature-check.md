---
title: "/INTEGRITYCHECK (Signaturpr&#252;fung erforderlich) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 9e738825-2c98-40cd-8ad2-5d0d9c14893e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# /INTEGRITYCHECK (Signaturpr&#252;fung erforderlich)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt an, dass die digitale Signatur des Binärimages zur Ladezeit überprüft werden muss.  
  
```  
/INTEGRITYCHECK[:NO]  
```  
  
## Hinweise  
 **\/INTEGRITYCHECK** ist standardmäßig deaktiviert.  
  
 Mit der **\/INTEGRITYCHECK**\-Option wird – im PE\-Header der DLL\-Datei oder der ausführbaren Datei – ein Flag festgelegt, damit der Speicher\-Manager eine Überprüfung auf eine digitale Signatur vornimmt, um das Image in Windows zu laden.  Diese Option muss für 32\-Bit\- und 64\-Bit\-DLLs festgelegt werden, die den Kernelmoduscode implementieren, der von bestimmten Windows\-Funktionen geladen wird, und wird für alle Gerätetreiber unter Windows Vista, [!INCLUDE[win7](../../build/includes/win7_md.md)], [!INCLUDE[win8](../../build/includes/win8_md.md)], [!INCLUDE[winsvr08](../../build/includes/winsvr08_md.md)] und [!INCLUDE[winserver8](../../build/includes/winserver8_md.md)] empfohlen.  Windows\-Versionen vor Windows Vista ignorieren dieses Flag.  Weitere Informationen finden Sie im Artikel zu [erzwungener Integritätssignierung von portierbaren ausführbaren Dateien \(Portable Executable, PE\)](http://social.technet.microsoft.com/wiki/contents/articles/255.forced-integrity-signing-of-portable-executable-pe-files.aspx).  
  
### So legen Sie diese Linkeroption in Visual Studio fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Weitere Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Erweitern Sie den Knoten **Konfigurationseigenschaften**.  
  
3.  Erweitern Sie den Knoten **Linker**.  
  
4.  Wählen Sie die Eigenschaftenseite **Befehlszeile** aus.  
  
5.  Geben Sie unter **Zusätzliche Optionen**`/INTEGRITYCHECK` oder `/INTEGRITYCHECK:NO` ein.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)   
 [Erzwungene Integritätssignierung von portierbaren ausführbaren Dateien \(Portable Executable, PE\)](http://social.technet.microsoft.com/wiki/contents/articles/255.forced-integrity-signing-of-portable-executable-pe-files.aspx)   
 [Exemplarische Vorgehensweise: Kernelmodus\-Codesignaturen](http://msdn.microsoft.com/windows/hardware/gg487328.aspx)   
 [AppInit\-DLLs in Windows 7 und Windows Server 2008](http://msdn.microsoft.com/windows/hardware/gg463040.aspx)