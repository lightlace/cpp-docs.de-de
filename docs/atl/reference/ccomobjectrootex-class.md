---
title: "CComObjectRootEx Class"
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
  - "ATL.CComObjectRootEx"
  - "ATL::CComObjectRootEx<ThreadModel>"
  - "CComObjectRootEx"
  - "ATL::CComObjectRootEx"
  - "ATL.CComObjectRootEx<ThreadModel>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "reference counting"
ms.assetid: 894a3d7c-2daf-4fd0-8fa4-e6a05bcfb631
caps.latest.revision: 20
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# CComObjectRootEx Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt Methoden zum Handleobjektverweis\-Anzahlverwaltung für nicht aggregiertes und zusammengesetzte Objekte bereit.  
  
## Syntax  
  
```  
  
      template<  
   class ThreadModel   
>  
class CComObjectRootEx : public CComObjectRootBase  
```  
  
#### Parameter  
 `ThreadModel`  
 Die Klasse, deren Methoden das gewünschte Threadingmodell implementieren.  Sie können das Threadingmodell explizit auswählen, indem Sie `ThreadModel` zu [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md), zu [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) oder zu [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md) festlegen.  Sie können das standardmäßige Threadmodell des Servers akzeptieren, indem Sie `ThreadModel` zu [CComObjectThreadModel](../Topic/CComObjectThreadModel.md) oder zu [CComGlobalsThreadModel](../Topic/CComGlobalsThreadModel.md) festlegen.  
  
## Mitglieder  
  
### Methoden  
  
|||  
|-|-|  
|[CComObjectRootEx](../Topic/CComObjectRootEx::CComObjectRootEx.md)|Konstruktor.|  
|[InternalAddRef](../Topic/CComObjectRootEx::InternalAddRef.md)|Inkrementiert den Verweiszähler für ein nicht aggregiertes Objekt.|  
|[InternalRelease](../Topic/CComObjectRootEx::InternalRelease.md)|Dekrementiert den Verweiszähler für ein nicht aggregiertes Objekt.|  
|[Sperren](../Topic/CComObjectRootEx::Lock.md)|Wenn das Threadmodell eine Multithreadkomponente ist, erhält den Besitz einer kritischen Abschnittsobjekts.|  
|[Entsperren Sie](../Topic/CComObjectRootEx::Unlock.md)|Wenn das Threadmodell eine Multithreadkomponente ist, gibt den Besitz einer kritischen Abschnittsobjekts frei.|  
  
### CComObjectRootBase\-Methoden  
  
|||  
|-|-|  
|[FinalConstruct](../Topic/CComObjectRootEx::FinalConstruct.md)|Überschreibung in der Klasse, um jede Initialisierung auszuführen erfordert durch das Objekt.|  
|[FinalRelease](../Topic/CComObjectRootEx::FinalRelease.md)|Überschreibung in der Klasse, um alle auszuführen bereinigen erforderliches durch das Objekt.|  
|[OuterAddRef](../Topic/CComObjectRootEx::OuterAddRef.md)|Inkrementiert den Verweiszähler für ein zusammengesetztes Objekt.|  
|[OuterQueryInterface](../Topic/CComObjectRootEx::OuterQueryInterface.md)|Delegaten zu äußeren **IUnknown** eines zusammengesetzten Objekts.|  
|[OuterRelease](../Topic/CComObjectRootEx::OuterRelease.md)|Dekrementiert den Verweiszähler für ein zusammengesetztes Objekt.|  
  
### Statische Funktionen  
  
|||  
|-|-|  
|[InternalQueryInterface](../Topic/CComObjectRootEx::InternalQueryInterface.md)|Delegaten zu **IUnknown** eines nicht aggregierten Objekts.|  
|[ObjectMain](../Topic/CComObjectRootEx::ObjectMain.md)|Aufgerufen während der Modulinitialisierung und \- beendung für die abgeleiteten Klassen aufgeführt in der Objektzuordnung.|  
  
### Datenmember  
  
|||  
|-|-|  
|[m\_dwRef](../Topic/CComObjectRootEx::m_dwRef.md)|Mit `m_pOuterUnknown` Teil einer Union.  Wird verwendet, wenn das Objekt nicht aggregiert wird, um den Verweiszähler von `AddRef` und von **Release** aufzunehmen.|  
|[m\_pOuterUnknown](../Topic/CComObjectRootEx::m_pOuterUnknown.md)|Mit `m_dwRef` Teil einer Union.  Wird verwendet, wenn das Objekt aggregiert wird, um einen Zeiger auf den äußeren Unbekannten aufzunehmen.|  
  
## Hinweise  
 `CComObjectRootEx` Handleobjektverweis\-Anzahlverwaltung für nicht aggregiertes und zusammengesetzte Objekte.  Sie enthält die Objektverweisanzahl, wenn das Objekt nicht aggregiert wird, und enthält den Zeiger des äußeren Unbekannten an, wenn das Objekt aggregiert wird.  Für zusammengesetzte Objekte können `CComObjectRootEx`\-Methoden verwendet werden, um den Fehler des inneren Objekts dem Konstrukt zu behandeln, und das äußere Objekt vom Löschen, wenn innere Schnittstellen freigegeben werden oder das innere Objekt zu schützen wird gelöscht.  
  
 Eine Klasse, die einen COM\-Server implementiert, muss von `CComObjectRootEx` oder von [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) erben.  
  
 Wenn die Klassendefinition das [DECLARE\_POLY\_AGGREGATABLE](../Topic/DECLARE_POLY_AGGREGATABLE.md)\-Makro angibt, ATL erstellt eine Instanz von **CComPolyObject\<CYourClass\>**, wenn **IClassFactory::CreateInstance** aufgerufen wird.  Bei der Erstellung wird der Wert des äußeren Unbekannten überprüft.  Wenn es **NULL** ist, wird **IUnknown** für ein aggregiertes Objekt nicht implementiert.  Wenn das äußere Unbekannte nicht **NULL** ist, wird **IUnknown** für ein zusammengesetztes Objekt implementiert.  
  
 Wenn die Klasse nicht das `DECLARE_POLY_AGGREGATABLE`\-Makro angibt, ATL erstellt eine Instanz von **CAggComObject\<CYourClass\>** für zusammengesetzte Objekte oder eine Instanz von **CComObject\<CYourClass\>** für nicht aggregierte Objekte.  
  
 Der Vorteil der Verwendung von `CComPolyObject` ist, dass Sie vermeiden, `CComAggObject` und `CComObject` im Modul verfügen, um die aggregierten und nicht aggregierten Fälle zu behandeln.  Einzelne `CComPolyObject`\-Objekthandles beide Fälle.  Daher bestehen nur eine Kopie des vtable und eine Kopie der Funktionen im Modul.  Wenn das vtable groß ist, kann dies die Modulgröße erheblich beeinträchtigt.  Wenn das vtable ist, mit `CComPolyObject` eine einige größere Modulgröße führen klein, da sie nicht für ein aggregiertes oder nicht aggregiertes Objekt optimiert wird, wie können `CComAggObject` und `CComObject`.  
  
 Wenn das Objekt aggregiert wird, wird [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) durch `CComAggObject` oder `CComPolyObject` implementiert.  Diese Klassen delegieren `QueryInterface`, `AddRef` und **Release**\-Aufrufe an `OuterQueryInterface`, `OuterAddRef` und `OuterRelease` von `CComObjectRootEx`, um an den äußeren Unbekannten weiterzuleiten.  In der Regel überschreiben Sie `CComObjectRootEx::FinalConstruct` in der Klasse, um alle zusammengesetzten Objekte zu erstellen und `CComObjectRootEx::FinalRelease` überschreiben, um zusammengesetzte Objekte freizugeben.  
  
 Wenn das Objekt nicht aggregiert wird, wird **IUnknown** durch `CComObject` oder `CComPolyObject` implementiert.  In diesem Fall werden Aufrufe von `QueryInterface`, `AddRef` und **Release** an `InternalQueryInterface`, `InternalAddRef` und `InternalRelease` von `CComObjectRootEx` delegiert, um die tatsächlichen Vorgänge auszuführen.  
  
## Anforderungen  
 **Header:**  möchten  
  
## Siehe auch  
 [CComAggObject Class](../../atl/reference/ccomaggobject-class.md)   
 [CComObject Class](../../atl/reference/ccomobject-class.md)   
 [CComPolyObject Class](../../atl/reference/ccompolyobject-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)