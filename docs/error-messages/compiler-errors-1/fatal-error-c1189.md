---
title: "Schwerwiegender Fehler C1189 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1189"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1189"
ms.assetid: 2e5c8a78-edd4-411c-b619-558a96be148a
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# Schwerwiegender Fehler C1189
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#error : benutzerdefinierte Fehlermeldung  
  
 C1189 wird von der `#error`\-Direktive generiert.  Der Entwickler, der die Direktive codiert, gibt den Text der Fehlermeldung an.  Weitere Informationen finden Sie unter [\#error\-Direktive](../../preprocessor/hash-error-directive-c-cpp.md).  
  
 Im folgenden Beispiel wird C1189 generiert.  In diesem Beispiel gibt der Entwickler eine benutzerdefinierte Fehlermeldung aus, da der `_WIN32`\-Bezeichner nicht definiert wurde:  
  
```  
// C1189.cpp  
#undef _WIN32  
#if !defined(_WIN32)  
#error _WIN32 must be defined   // C1189  
#endif  
```  
  
 Dieser Fehler wird auch angezeigt, wenn Sie mit der **\/robust**\-Option des MIDL\-Compilers ein ATL\-Projekt erstellen.  Verwenden Sie den Schalter **\/robust**, um nur [!INCLUDE[win2kfamily](../../c-runtime-library/includes/win2kfamily_md.md)] und höheren Versionen von Windows zu erstellen.  Um diesen Fehler zu korrigieren, verwenden Sie eine der folgenden Prozeduren:  
  
-   Ändern Sie diese Zeile in der Datei dlldatax.c:  
  
```  
#define _WIN32_WINNT 0x0400   // for WinNT 4.0 or Windows 95 with DCOM  
```  
  
 in:  
  
```  
#define _WIN32_WINNT 0x0500   // for WinNT 4.0 or Windows 95 with DCOM  
```  
  
-   Verwenden Sie die Eigenschaftenseite **Erweitert** im Eigenschaftenseitenordner **MIDL**, um den **\/robust**\-Schalter zu entfernen und dann den **\/no\_robust**\-Schalter anzugeben.  Weitere Informationen finden Sie unter [Eigenschaftenseiten "MIDL": "Erweitert"](../../ide/midl-property-pages-advanced.md).  
  
## Siehe auch  
 [\#define\-Direktive](../../preprocessor/hash-define-directive-c-cpp.md)