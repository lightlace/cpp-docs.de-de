---
title: "IPersistStorageImpl Class"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "ATL::IPersistStorageImpl"
  - "ATL::IPersistStorageImpl<T>"
  - "ATL.IPersistStorageImpl<T>"
  - "IPersistStorageImpl"
  - "ATL.IPersistStorageImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IPersistStorageImpl class"
  - "Speicher, ATL"
ms.assetid: d652f02c-239c-47c7-9a50-3e9fc3014fff
caps.latest.revision: 20
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# IPersistStorageImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse implementiert die Schnittstelle [IPersistStorage](http://msdn.microsoft.com/library/windows/desktop/ms679731).  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausführen.  
  
## Syntax  
  
```  
  
      template <  
class T  
>  
class ATL_NO_VTABLE IPersistStorageImpl :  
public IPersistStorage  
```  
  
#### Parameter  
 `T`  
 Die Klasse, die von abgeleitet `IPersistStorageImpl`.  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[IPersistStorageImpl::GetClassID](../Topic/IPersistStorageImpl::GetClassID.md)|Ruft die CLSID des Objekts ab.|  
|[IPersistStorageImpl::HandsOffStorage](../Topic/IPersistStorageImpl::HandsOffStorage.md)|Weist das Objekt auf, um alle Speicherobjekte freizugeben und HandsOff\-Modus einzugeben.  Die ATL\-Implementierung gibt `S_OK` zurück.|  
|[IPersistStorageImpl::InitNew](../Topic/IPersistStorageImpl::InitNew.md)|Initialisiert einen neuen Speicher.|  
|[IPersistStorageImpl::IsDirty](../Topic/IPersistStorageImpl::IsDirty.md)|Überprüft, ob die Daten des Objekts geändert haben, seit der zuletzt gespeichert wurde.|  
|[IPersistStorageImpl::Load](../Topic/IPersistStorageImpl::Load.md)|Lädt die Eigenschaften des Objekts vom angegebenen Speicher.|  
|[IPersistStorageImpl::Save](../Topic/IPersistStorageImpl::Save.md)|Speichert die Eigenschaften des Objekts mit dem angegebenen Speicher.|  
|[IPersistStorageImpl::SaveCompleted](../Topic/IPersistStorageImpl::SaveCompleted.md)|Meldet ein Objekt, dass den normalen Modus zurückgeben kann, um auf den Speicherobjekt zu schreiben.  Die ATL\-Implementierung gibt `S_OK` zurück.|  
  
## Hinweise  
 `IPersistStorageImpl` [IPersistStorage](http://msdn.microsoft.com/library/windows/desktop/ms679731) implementiert die Schnittstelle, die einem Client ermöglicht, dass die anzufordern Objektlast und seine persistenten Daten mithilfe eines Speichers gespeichert werden.  
  
 Die Implementierung dieser Klasse benötigt Klasse `T`, eine Implementierung der Schnittstelle `IPersistStreamInit` auszuführen, die über `QueryInterface` verfügbar ist.  In der Regel bedeutet dies, dass `T`[IPersistStreamInitImpl](../../atl/reference/ipersiststreaminitimpl-class.md)\-Klasse von ableiten, einen Eintrag für `IPersistStreamInit` in [COM\-Zuordnung](../Topic/BEGIN_COM_MAP.md) bereitstellen, und [Eigenschaftenzuordnung](../Topic/BEGIN_PROP_MAP.md) verwenden soll, um die persistenten Daten der Klasse zu beschreiben.  
  
 **Verwandte Elemente** [ATL\-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL\-Projekts](../../atl/reference/creating-an-atl-project.md)  
  
## Vererbungshierarchie  
 `IPersistStorage`  
  
 `IPersistStorageImpl`  
  
## Anforderungen  
 **Header:**  möchten  
  
## Siehe auch  
 [Storages and Streams](http://msdn.microsoft.com/library/windows/desktop/aa380352)   
 [IPersistStreamInitImpl Class](../../atl/reference/ipersiststreaminitimpl-class.md)   
 [IPersistPropertyBagImpl Class](../../atl/reference/ipersistpropertybagimpl-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)