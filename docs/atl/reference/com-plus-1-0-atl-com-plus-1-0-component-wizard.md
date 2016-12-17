---
title: "COM+ 1.0, ATL COM+ 1.0-Komponenten-Assistent"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "vc.codewiz.class.atl.mts.options"
dev_langs: 
  - "C++"
ms.assetid: 2fbe259c-6be1-4d0e-9cfe-721c75c97cb1
caps.latest.revision: 11
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# COM+ 1.0, ATL COM+ 1.0-Komponenten-Assistent
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Auf dieser Seite des ATL COM\+ 1.0 Komponenten\-Assistenten können Sie den Schnittstellentyp sowie zusätzliche Schnittstellen festlegen, die unterstützt werden sollen.  
  
 Weitere Informationen zu ATL\-Projekten und ATL\-COM\-Klassen finden Sie unter [ATL COM Desktop Components](../../atl/atl-com-desktop-components.md).  
  
 **Interface**  
 Gibt den Typ der Schnittstelle an, die vom Objekt unterstützt wird.  Das Objekt unterstützt standardmäßig eine duale Schnittstelle.  
  
|Option|Description|  
|------------|-----------------|  
|**Dual**|Gibt an, dass das Objekt eine duale Schnittstelle unterstützt \(die **vtable** des Objekts enthält benutzerdefinierte Schnittstellenfunktionen sowie `IDispatch`\-Methoden für spätes Binden\).  Ermöglicht sowohl COM\-Clients als auch Automatisierungscontrollern den Zugriff auf das Objekt.|  
|**Benutzerdefiniert**|Gibt an, dass das Objekt eine benutzerdefinierte Schnittstelle unterstützt \(die **vtable** des Objekts enthält benutzerdefinierte Schnittstellenfunktionen\).  Eine benutzerdefinierte Schnittstelle ist, insbesondere über Prozessgrenzen hinweg, schneller als eine duale Schnittstelle.<br /><br /> -   **Automatisierungskompatibel** fügt Automatisierungsunterstützung der benutzerdefinierten Schnittstelle hinzu.  Legen Sie für attributierte Projekte das **oleautomation**\-Attribut in der Co\-Klasse fest.|  
  
 **Warteschlangenfähig**  
 Gibt an, dass Clients diese Komponente unter Verwendung von Meldungswarteschlangen asynchron aufrufen können.  Fügt der H\-Datei \(attributierte Projekte\) oder der IDL\-Datei \(nicht attributierte Projekte\) das custom\(TLBATTR\_QUEUEABLE, 0\)\-Komponentenattributmakro hinzu.  
  
 **Unterstützung**  
 Gibt an, ob zusätzliche Unterstützung für die Fehlerbehandlung und Objektsteuerung verfügbar ist.  
  
|Option|Description|  
|------------|-----------------|  
|**ISupportErrorInfo**|Richtet die Unterstützung für die [ISupportErrorInfo](../../atl/reference/isupporterrorinfoimpl-class.md)\-Schnittstelle ein, sodass das Objekt Fehlerinformationen an den Client zurückgeben kann.|  
|**IObjectControl**|Ermöglicht dem Objekt Zugriff auf die folgenden drei [IObjectControl](http://msdn.microsoft.com/library/windows/desktop/ms686474)\-Methoden: [Activate](http://msdn.microsoft.com/library/windows/desktop/ms681303), [CanBePooled](http://msdn.microsoft.com/library/windows/desktop/ms684322) und [Deactivate](http://msdn.microsoft.com/library/windows/desktop/ms687094).|  
|**IObjectConstruct**|Implementiert Unterstützung für die [IObjectConstruct](http://msdn.microsoft.com/library/windows/desktop/ms680583)\-Schnittstelle, die die Parameterübergabe von anderen Methoden oder Objekten verwaltet.|  
  
 **Transaktion**  
 Gibt an, dass das Objekt Transaktionen unterstützt,  und fügt der IDL\-Datei \(nicht attributierte Projekte\) die Datei **mtxattr.h** hinzu.  
  
|Option|Description|  
|------------|-----------------|  
|**Unterstützt**|Legt fest, dass das Objekt niemals das Stammobjekt eines Transaktionsstreams ist. Dazu wird der H\-Datei \(attributierte Projekte\) oder der IDL\-Datei \(nicht attributierte Projekte\) das **custom\(TLBATTR\_TRANS\_SUPPORTED,0\)**\-Komponentenattributmakro hinzugefügt.|  
|**Erforderlich**|Legt fest, dass das Objekt das Stammobjekt eines Transaktionsstreams sein kann oder nicht. Dazu wird der H\-Datei \(attributierte Projekte\) oder der IDL\-Datei \(nicht attributierte Projekte\) das **custom\(TLBATTR\_TRANS\_REQUIRED,0\)**\-Komponentenattributmakro hinzugefügt.|  
|**Nicht unterstützt**|Gibt an, dass das Objekt Transaktionen ausschließt.  Fügt der H\-Datei \(attributierte Projekte\) oder der IDL\-Datei \(nicht attributierte Projekte\) das **custom\(TLBATTR\_TRANS\_NOTSUPP,0\)**\-Komponentenattributmakro hinzu.|  
|**Neu erforderlich**|Legt fest, dass das Objekt immer das Stammobjekt eines Transaktionsstreams ist. Dazu wird der H\-Datei \(attributierte Projekte\) oder der IDL\-Datei \(nicht attributierte Projekte\) das **custom\(TLBATTR\_TRANS\_REQNEW,0\)**\-Komponentenattributmakro hinzugefügt.|  
  
## Siehe auch  
 [ATL COM\+ 1.0 Komponenten\-Assistent](../../atl/reference/atl-com-plus-1-0-component-wizard.md)   
 [ATL COM\+ 1.0 Component](../../atl/reference/adding-an-atl-com-plus-1-0-component.md)