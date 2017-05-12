---
title: "Attribute (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4438e03c-4de3-433d-abcc-31aa863bc0e0
caps.latest.revision: 8
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 8
---
# Attribute (C++/CX)
Ein Attribut ist eine spezielle Verweisklasse, die [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Typen und \-Methoden in eckigen vorangestellt werden kann, um bestimmte Verhalten bei der Metadatenerstellung anzugeben. Mehrere vordefinierte Attribute, z. B. [Windows::Foundation::Metadata::WebHostHidden](http://msdn.microsoft.com/library/windows/apps/windows.foundation.metadata.webhosthiddenattribute.aspx), werden häufig in [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\-Code verwendet. Dieses Beispiel zeigt, wie das Attribut auf eine Klasse angewendet wird:  
  
 [!code-cpp[cx_attributes#01](../snippets/cpp/VS_Snippets_Misc/cx_attributes/cpp/class1.h#01)]  
  
## Benutzerdefinierte Attribute  
 Sie können auch benutzerdefinierte Attribute definieren. Benutzerdefinierte Attribute müssen diesen [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] Regeln entsprechen:  
  
-   Benutzerdefinierte Attribute können nur öffentliche Felder enthalten.  
  
-   Benutzerdefinierte Attributfelder können initialisiert werden, wenn das Attribut auf eine Klasse angewendet wird.  
  
-   Ein Feld kann einer dieser Typen sein:  
  
    -   int32 \(int\)  
  
    -   uint32 \(int ohne Vorzeichen\)  
  
    -   bool  
  
    -   Platform::String^  
  
    -   Windows::Foundation::HResult  
  
    -   Platform::Type^  
  
    -   öffentliche Enumerationsklasse \(enthält benutzerdefinierte Enumerationen\)  
  
 Das nächste Beispiel zeigt, wie ein benutzerdefiniertes Attribut definiert und anschließend zur Verwendung initialisiert wird.  
  
 [!code-cpp[cx_attributes#02](../snippets/cpp/VS_Snippets_Misc/cx_attributes/cpp/class1.h#02)]  
  
## Siehe auch  
 [Typsystem \(C\+\+\/CX\)](../cppcx/type-system-c-cx.md)   
 [Sprachreferenz zu Visual C\+\+](../cppcx/visual-c-language-reference-c-cx.md)   
 [Namespaceverweis](../cppcx/namespaces-reference-c-cx.md)