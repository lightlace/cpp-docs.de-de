---
title: COM+ 1.0, ATL COM+ 1.0-Assistenten | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.mts.options
dev_langs:
- C++
ms.assetid: 2fbe259c-6be1-4d0e-9cfe-721c75c97cb1
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 36295e5ce296ea6ba982c4ce8cf729bf45860883
ms.lasthandoff: 02/24/2017

---
# <a name="com-10-atl-com-10-component-wizard"></a>COM+ 1.0, ATL COM+ 1.0-Komponenten-Assistent
Verwenden Sie auf dieser Seite des ATL COM+ 1.0 Komponenten-Assistenten, geben Sie den Typ und weitere Schnittstellen unterstützt werden.  
  
 Weitere Informationen zu ATL-Projekten und ATL-COM-Klassen finden Sie unter [Desktop-Komponenten von ATL-COM-](../../atl/atl-com-desktop-components.md).  
  
 **Benutzeroberfläche**  
 Gibt den Typ der Schnittstelle, die das Objekt unterstützt. Das Objekt unterstützt standardmäßig eine duale Schnittstelle.  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**Zwei**|Gibt an, dass das Objekt eine duale Schnittstelle unterstützt (die vtable des Objekts enthält, benutzerdefinierte Schnittstellenfunktionen sowie spätes Binden `IDispatch` Methoden). Ermöglicht sowohl COM-Clients als auch Automatisierungscontrollern den Zugriff auf das Objekt.|  
|**Benutzerdefinierte**|Gibt an, dass das Objekt eine benutzerdefinierte Schnittstelle unterstützt (die vtable des Objekts enthält benutzerdefinierte Schnittstellenfunktionen). Eine benutzerdefinierte Schnittstelle kann insbesondere über Prozessgrenzen hinweg schneller als eine duale Schnittstelle sein.<br /><br /> -   **Automatisierung kompatibel** die benutzerdefinierte Schnittstelle Benutzeroberflächenautomatisierungs-Unterstützung hinzugefügt. Legt für die attributierte Projekte die **Oleautomation** -Attribut in der Co-Klasse.|  
  
 **Queueable**  
 Gibt an, dass Clients diese Komponente mit Meldungswarteschlangen asynchron aufrufen können. Fügt die Komponente attributiert Custom (TLBATTR_QUEUEABLE-Komponentenattributmakro, 0), der h-Datei (attributierte Projekte) oder der IDL-Datei (nicht attributierte Projekte).  
  
 **Unterstützung**  
 Gibt zusätzliche Unterstützung für Fehler behandeln und Objekt-Steuerelement an.  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**ISupportErrorInfo**|Unterstützung für die [ISupportErrorInfo](../../atl/reference/isupporterrorinfoimpl-class.md) Schnittstelle, damit das Objekt Fehlerinformationen an den Client zurückgeben kann.|  
|**IObjectControl**|Ermöglicht dem Objektzugriff auf die drei [IObjectControl](http://msdn.microsoft.com/library/windows/desktop/ms686474) Methoden: [aktivieren](http://msdn.microsoft.com/library/windows/desktop/ms681303), [CanBePooled](http://msdn.microsoft.com/library/windows/desktop/ms684322), und [deaktivieren](http://msdn.microsoft.com/library/windows/desktop/ms687094).|  
|**IObjectConstruct**|Unterstützung für die [IObjectConstruct](http://msdn.microsoft.com/library/windows/desktop/ms680583) Schnittstelle übergeben Parameter von anderen Methoden oder Objekten verwaltet.|  
  
 **Transaktion**  
 Gibt an, dass das Objekt Transaktionen unterstützt. Die mtxattr.h Datei IDL-Datei (nicht attributierte Projekte).  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**Unterstützt**|Gibt an, dass das Objekt niemals das Stammobjekt einer Transaktion von der Komponente Attribut-Makro custom(TLBATTR_TRANS_SUPPORTED,0) .h-Datei (attributierte Projekte) oder der IDL-Datei (nicht attributierte Projekte) hinzugefügt werden.|  
|**Erforderlich**|Gibt an, dass das Objekt möglicherweise oder sind möglicherweise nicht auf das Stammobjekt einer Transaktion durch die Komponente Attribut-Makro custom(TLBATTR_TRANS_REQUIRED,0) .h-Datei (attributierte Projekte) oder der IDL-Datei (nicht attributierte Projekte) hinzugefügt werden.|  
|**Nicht unterstützt**|Gibt an, dass das Objekt Transaktionen ausschließt. Fügt der Custom(TLBATTR_TRANS_NOTSUPP,0)-Komponentenattributmakro hinzu, der h-Datei (attributierte Projekte) oder der IDL-Datei (nicht attributierte Projekte).|  
|**Erfordert neu**|Gibt an, dass das Objekt immer das Stammobjekt einer Transaktion von der Komponente Attribut-Makro custom(TLBATTR_TRANS_REQNEW,0) .h-Datei (attributierte Projekte) oder der IDL-Datei (nicht attributierte Projekte) hinzugefügt werden.|  
  
## <a name="see-also"></a>Siehe auch  
 [ATL COM+ 1.0 Komponenten-Assistent](../../atl/reference/atl-com-plus-1-0-component-wizard.md)   
 [ATL COM+ 1.0-Komponente](../../atl/reference/adding-an-atl-com-plus-1-0-component.md)


