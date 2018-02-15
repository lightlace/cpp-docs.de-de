---
title: Attribute (C + c++ / CX) | Microsoft Docs
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
ms.assetid: 4438e03c-4de3-433d-abcc-31aa863bc0e0
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 332b3ddfc2c6e414ebd0a650357f0cb97657b399
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="attributes-ccx"></a>Attribute (C++/CX)
Ein Attribut ist eine spezielle Verweisklasse, die in Windows-Runtime-Typen und Methoden, um bestimmte Verhalten bei der Metadatenerstellung anzugeben eckigen vorangestellt werden kann. Mehrere vordefinierte Attribute – beispielsweise [Windows::Foundation::Metadata::WebHostHidden](http://msdn.microsoft.com/library/windows/apps/windows.foundation.metadata.webhosthiddenattribute.aspx)– werden häufig verwendet, in C + c++ / CX-Code. Dieses Beispiel zeigt, wie das Attribut auf eine Klasse angewendet wird:  
  
 [!code-cpp[cx_attributes#01](../cppcx/codesnippet/CPP/cx_attributes/class1.h#01)]  
  
## <a name="custom-attributes"></a>Benutzerdefinierte Attribute  
 Sie können auch benutzerdefinierte Attribute definieren. Benutzerdefinierte Attribute müssen diesen Windows-Runtime-Regeln entsprechen:  
  
-   Benutzerdefinierte Attribute können nur öffentliche Felder enthalten.  
  
-   Benutzerdefinierte Attributfelder können initialisiert werden, wenn das Attribut auf eine Klasse angewendet wird.  
  
-   Ein Feld kann einer dieser Typen sein:  
  
    -   int32 (int)  
  
    -   uint32 (int ohne Vorzeichen)  
  
    -   bool  
  
    -   Platform::String^  
  
    -   Windows::Foundation::HResult  
  
    -   Platform::Type^  
  
    -   öffentliche Enumerationsklasse (enthält benutzerdefinierte Enumerationen)  
  
 Das nächste Beispiel zeigt, wie ein benutzerdefiniertes Attribut definiert und anschließend zur Verwendung initialisiert wird.  
  
 [!code-cpp[cx_attributes#02](../cppcx/codesnippet/CPP/cx_attributes/class1.h#02)]  
  
## <a name="see-also"></a>Siehe auch  
 [Typsystem (C++/CX)](../cppcx/type-system-c-cx.md)   
 [Visual C++-Sprachreferenz](../cppcx/visual-c-language-reference-c-cx.md)   
 [Namespaceverweis](../cppcx/namespaces-reference-c-cx.md)