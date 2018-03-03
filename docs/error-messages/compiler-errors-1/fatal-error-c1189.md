---
title: Schwerwiegender Fehler C1189 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1189
dev_langs:
- C++
helpviewer_keywords:
- C1189
ms.assetid: 2e5c8a78-edd4-411c-b619-558a96be148a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2330d49f817012fc2e0381a0991f709ada74ea32
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1189"></a>Schwerwiegender Fehler C1189
\#Fehler: benutzerdefinierte Fehlermeldung  
  
 C1189 wird generiert, indem die `#error` Richtlinie. Der Entwickler, der die Direktive codes gibt den Text der Fehlermeldung. Weitere Informationen finden Sie unter [#error-Direktive (C/C++)](../../preprocessor/hash-error-directive-c-cpp.md).  
  
 Im folgenden Beispiel wird C1189 generiert. In diesem Beispiel gibt der Entwickler eine benutzerdefinierte Fehlermeldung, da die `_WIN32` Bezeichner ist nicht definiert:  
  
```  
// C1189.cpp  
#undef _WIN32  
#if !defined(_WIN32)  
#error _WIN32 must be defined   // C1189  
#endif  
```  
  
 Dieser Fehler wird möglicherweise auch dann angezeigt, wenn ein ATL-Projekts zu erstellen, mit der **/ stabile** MIDL-Compileroption. Verwenden der **/ stabile** Switch nur erstellen [!INCLUDE[win2kfamily](../../c-runtime-library/includes/win2kfamily_md.md)] und höheren Versionen von Windows. Verwenden Sie eines der folgenden Verfahren an, um diesen Fehler zu beheben:  
  
-   Ändern Sie diese Zeile in der Datei dlldatax.c:  
  
```  
#define _WIN32_WINNT 0x0400   // for WinNT 4.0 or Windows 95 with DCOM  
```  
  
 in:  
  
```  
#define _WIN32_WINNT 0x0500   // for WinNT 4.0 or Windows 95 with DCOM  
```  
  
-   Verwenden der **erweitert** Eigenschaftenseite in der **"MIDL"** zu entfernenden Eigenschaft Seite Ordners der **/ stabile** wechseln, und geben Sie dann die **/no_robust** wechseln. Weitere Informationen finden Sie unter [Eigenschaftenseiten "MIDL": erweiterte](../../ide/midl-property-pages-advanced.md).  
  
## <a name="see-also"></a>Siehe auch  
 [#define-Direktive (C/C++)](../../preprocessor/hash-define-directive-c-cpp.md)