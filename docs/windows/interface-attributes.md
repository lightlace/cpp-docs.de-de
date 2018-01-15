---
title: Schnittstellenattribut | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- attributes [C++], reference topics
- interface attributes
ms.assetid: 27fcdfee-abce-4585-8b53-ee31635356e8
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5ff84939b3211633e199066e1a38da2e91efb1c8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="interface-attributes"></a>Schnittstellenattribut
Die folgenden Attribute gelten für die [-Schnittstelle (oder __interface)](../cpp/interface.md) C++-Schlüsselwort.  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|[async_uuid](../windows/async-uuid.md)|Gibt an, die synchrone und asynchrone Versionen einer COM-Schnittstelle definiert die MIDL-Compiler anweist, UUID.|  
|[benutzerdefinierte](../windows/custom-cpp.md)|Ermöglicht Ihnen das Definieren eigener Attribute.|  
|[dispinterface](../windows/dispinterface.md)|Fügt eine Schnittstelle in die IDL-Datei als Verteilschnittstelle ein.|  
|[dual](../windows/dual.md)|Fügt eine Schnittstelle in der IDL-Datei als eine duale Schnittstelle.|  
|[export](../windows/export.md)|Bewirkt, dass eine Datenstruktur, in der IDL-Datei abgelegt werden soll.|  
|[helpcontext](../windows/helpcontext.md)|Gibt eine Kontext-ID, mit dem die Benutzerinformationen zu diesem Element in der Hilfedatei.|  
|[helpfile](../windows/helpfile.md)|Legt den Namen der Hilfedatei für eine Typbibliothek.|  
|[helpstring](../windows/helpstring.md)|Gibt eine Zeichenfolge, die verwendet wird, um das Element zu beschreiben, auf dem es angewendet.|  
|[helpstringcontext](../windows/helpstringcontext.md)|Gibt die ID des Hilfethemas in einer HLP oder CHM-Datei an.|  
|[helpstringdll](../windows/helpstringdll.md)|Gibt den Namen der DLL zu verwenden, um das Dokument Zeichenfolgensuche (Lokalisierung) ausführen.|  
|[hidden](../windows/hidden.md)|Gibt an, dass das Element vorhanden ist, aber nicht in einem Browser benutzerorientierte angezeigt werden soll.|  
|[library_block](../windows/library-block.md)|Fügt ein Konstrukt in der IDL-Datei bibliotheksblock vor.|  
|[lokale](../windows/local-cpp.md)|Können Sie die MIDL-Compiler als bei der Verwendung in der Schnittstelle Header einen Header-Generator zu verwenden. Wenn in einer einzelnen Funktion verwendet wird, kennzeichnet eine lokale Prozedur für die keine Stubs generiert werden.|  
|[nonextensible](../windows/nonextensible.md)|Gibt an, dass die `IDispatch` Implementierung enthält nur die Eigenschaften und Methoden aufgelistet, die in die schnittstellenbeschreibung und können nicht mit zusätzlichen Elementen zur Laufzeit erweitert werden. Dieses Attribut ist nur gültig für eine [duale](../windows/dual.md) Schnittstelle.|  
|[odl](../windows/odl.md)|Identifiziert eine Schnittstelle als Schnittstelle Objekt Description Language (ODL).|  
|[object](../windows/object-cpp.md)|Identifiziert eine benutzerdefinierte Schnittstelle an.|  
|[oleautomation](../windows/oleautomation.md)|Gibt an, dass eine Schnittstelle mit der Automatisierung kompatibel ist.|  
|[pointer_default](../windows/pointer-default.md)|Gibt das Standardattribut für die Zeiger für alle Zeiger mit Ausnahme der obersten Ebene Zeigern, die angezeigt werden in Parameterlisten an.|  
|[ptr](../windows/ptr.md)|Kennzeichnet einen Zeiger als vollständige Zeiger.|  
|[restricted](../windows/restricted.md)|Legt fest, welche Member in der Bibliothek nach dem Zufallsprinzip aufgerufen werden können.|  
|[UUID](../windows/uuid-cpp-attributes.md)|Stellt die eindeutige ID für die Bibliothek|  
  
 Sie müssen diese Regeln zum Definieren einer Schnittstelle beachten:  
  
-   Standardaufrufkonvention ist [__stdcall](../cpp/stdcall.md).  
  
-   Eine GUID wird für Sie bereitgestellt, wenn Sie eine nicht angeben.  
  
-   Es sind keine überladenen Methoden zulässig.  
  
 Wenn keine Angabe der [Uuid](../windows/uuid-cpp-attributes.md) Attribut, und verwenden den gleichen Schnittstellennamen in Projekten anderes Attribut, wird dieselbe GUID generiert.  
  
## <a name="see-also"></a>Siehe auch  
 [Attribute nach Verwendung](../windows/attributes-by-usage.md)