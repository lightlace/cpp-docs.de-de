---
title: "/CLRHEADER"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "/CLRHEADER"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/CLRHEADER (dumpbin-Option)"
  - "CLRHEADER (dumpbin-Option)"
  - "-CLRHEADER (dumpbin-Option)"
ms.assetid: cf73424f-4541-47e2-b94e-69b95266ef2a
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# /CLRHEADER
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/CLRHEADER file  
```  
  
## Hinweise  
 Hierbei ist:  
  
 `file`  
 Eine mit [\/clr](../../build/reference/clr-common-language-runtime-compilation.md) erstellte Abbilddatei.  
  
## Hinweise  
 **CLRHEADER** zeigt Informationen über die in verwalteten Programmen verwendeten .NET\-Header an.  Die Ausgabe zeigt Position und Größe des .NET\-Headers \(in Bytes\) sowie Abschnitte im Header an.  
  
 Für Dateien, die mit der [\/GL](../../build/reference/gl-whole-program-optimization.md)\-Compileroption erstellt wurden, kann nur die DUMPBIN\-Option [\/HEADERS](../../build/reference/headers.md) verwendet werden.  
  
 Wenn \/CLRHEADER bei einer mit \/clr kompilierten Datei verwendet wird, ist in der dumpbin\-Ausgabe der Abschnitt **clr Header:** enthalten.  Der Wert von **flags** gibt an, welche \/clr\-Option verwendet wurde:  
  
-   0  \-\- \/clr \(Abbild enthält möglicherweise systemeigenen Code\).  
  
-   1 \-\- \/clr:safe \(Abbild ist nur MSIL, kompatibel mit allen CLR\-Plattformen und möglicherweise überprüfbar\).  
  
-   3 \-\- \/clr:pure \(Abbild ist nur MSIL, kann jedoch nur auf x86\-Plattformen ausgeführt werden\).  
  
 Sie können auch programmgesteuert überprüfen, ob ein Abbild für Common Language Runtime erstellt wurde.  Weitere Informationen finden Sie unter [Gewusst wie: Ermitteln, ob ein Bild systemeigen oder CLR ist](../../dotnet/how-to-determine-if-an-image-is-native-or-clr.md).  
  
## Siehe auch  
 [DUMPBIN\-Optionen](../../build/reference/dumpbin-options.md)