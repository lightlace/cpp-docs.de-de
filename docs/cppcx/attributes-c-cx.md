---
title: Attribute (C++ / CX) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 4438e03c-4de3-433d-abcc-31aa863bc0e0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 491b3cabd8003664a34543d8bb7a640759bd50ee
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43765020"
---
# <a name="attributes-ccx"></a>Attribute (C++/CX)
Ein Attribut ist eine besondere Art von Ref-Klasse, die in eckigen Klammern auf Windows-Runtime-Typen und Methoden, um bestimmte Verhalten bei der Metadatenerstellung anzugeben vorangestellt werden kann. Mehrere vordefinierte Attribute, z. B. [Windows::Foundation::Metadata::WebHostHidden](https://msdn.microsoft.com/library/windows/apps/windows.foundation.metadata.webhosthiddenattribute.aspx)– werden häufig verwendet, in C++ / CX-Code. Dieses Beispiel zeigt, wie das Attribut auf eine Klasse angewendet wird:  
  
 [!code-cpp[cx_attributes#01](../cppcx/codesnippet/CPP/cx_attributes/class1.h#01)]  
  
## <a name="custom-attributes"></a>Benutzerdefinierte Attribute  
 Sie können auch benutzerdefinierte Attribute definieren. Benutzerdefinierte Attribute müssen diese Windows-Runtime-Regeln entsprechen:  
  
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
 [Sprachreferenz zu Visual C++](../cppcx/visual-c-language-reference-c-cx.md)   
 [Namespaceverweis](../cppcx/namespaces-reference-c-cx.md)