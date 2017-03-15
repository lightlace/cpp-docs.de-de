---
title: "/CLRUNMANAGEDCODECHECK (Hinzuf&#252;gen von SuppressUnmanagedCodeSecurity-Attribut) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/CLRUNMANAGEDCODECHECK"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/CLRUNMANAGEDCODECHECK (Linkeroption)"
  - "-CLRUNMANAGEDCODECHECK (Linkeroption)"
ms.assetid: 73abc426-dab0-45e2-be85-0f9a14206cc2
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# /CLRUNMANAGEDCODECHECK (Hinzuf&#252;gen von SuppressUnmanagedCodeSecurity-Attribut)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**\/CLRUNMANAGEDCODECHECK** gibt an, ob vom Linker <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> auf Linker\-generierte `PInvoke`\-Aufrufe von verwaltetem Code in systemeigene DLLs angewendet werden soll.  
  
## Syntax  
  
```  
/CLRUNMANAGEDCODECHECK[:NO]  
```  
  
## Hinweise  
 Standardmäßig übernimmt der Linker den SuppressUnmanagedCodeSecurityAttribute für Linker\-generierte `PInvoke`\-Aufrufe.  Wenn **\/CLRUNMANAGEDCODECHECK** gültig ist, wird SuppressUnmanagedCodeSecurityAttribute nicht übernommen.  
  
 Das Attribut wird vom Linker nur Objekten hinzugefügt, die mit **\/clr** oder **\/clr:pure** kompiliert werden.  Vom Linker werden keine `PInvoke`\-Aufrufe in Objekten erzeugt, die mit **\/clr:safe** kompiliert werden.  Weitere Informationen finden Sie unter [\/clr \(Common Language Runtime\-Kompilierung\)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
 Ein `PInvoke`\-Aufruf wird erzeugt, wenn vom Linker kein verwaltetes, jedoch ein systemeigenes Symbol gefunden wird, das einem Verweis in einer aufrufenden verwalteten Funktion entspricht.  Weitere Informationen zu `PInvoke` finden Sie unter [Aufrufen systemeigener Funktionen aus verwaltetem Code](../../dotnet/calling-native-functions-from-managed-code.md).  
  
 Beachten Sie, dass bei Verwendung von <xref:System.Security.AllowPartiallyTrustedCallersAttribute> im Code **\/CLRUNMANAGEDCODECHECK** explizit festgelegt werden sollte.  Wenn ein Bild sowohl das SuppressUnmanagedCodeSecurity\-Attribut als auch das AllowPartiallyTrustedCallers\-Attribut enthält, stellt dies unter Umständen ein Sicherheitsrisiko dar.  
  
 Weitere Informationen über die Auswirkungen des SuppressUnmanagedCodeSecurity\-Attributs finden Sie unter [Security Optimizations](assetId:///cf255069-d85d-4de3-914a-e4625215a7c0).  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Erweitern Sie den Knoten **Konfigurationseigenschaften**.  
  
3.  Erweitern Sie den Knoten **Linker**.  
  
4.  Wählen Sie die Eigenschaftenseite **Erweitert** aus.  
  
5.  Ändern Sie die Eigenschaft **Nicht verwalteten CLR\-Code überprüfen**.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRUnmanagedCodeCheck*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)