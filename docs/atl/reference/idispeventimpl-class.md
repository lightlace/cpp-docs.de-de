---
title: "IDispEventImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IDispEventImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDispEventImpl class"
ms.assetid: a64b5288-35cb-4638-aad6-2d15b1c7cf7b
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# IDispEventImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt Implementierungen der `IDispatch`\-Methoden.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausführen.  
  
## Syntax  
  
```  
  
      template <  
UINT nID,  
class T,  
const IID* pdiid= &IID_NULL,  
const GUID* plibid= &GUID_NULL,  
WORD wMajor= 0,  
WORD wMinor= 0,  
class tihclass= CcomTypeInfoHolder  
>  
class ATL_NO_VTABLE IDispEventImpl :  
public IDispEventSimpleImpl<nID, T, pdiid>  
```  
  
#### Parameter  
 `nID`  
 Ein eindeutiger Bezeichner für das Quellobjekt.  Wenn `IDispEventImpl` die Basisklasse für ein zusammengesetztes Steuerelement ist, verwenden Sie das Ressourcen\-ID des gewünschten enthaltenden Steuerelements für diesen Parameter.  In anderen Fällen verwenden Sie eine beliebige positive ganze Zahl.  
  
 `T`  
 Die Klasse des Benutzers, die von `IDispEventImpl` abgeleitet wird.  
  
 `pdiid`  
 Der Zeiger auf IID der Ereignisdispatchschnittstelle implementiert von dieser Klasse.  Diese Schnittstelle muss in der Typbibliothek definiert sind, die von `plibid`, `wMajor` und `wMinor` angibt.  
  
 `plibid`  
 Ein Zeiger auf die Typbibliothek, die die Dispatchschnittstelle definiert, wird auf `pdiid` durch.  Wenn **&GUID\_NULL**, die Typbibliothek vom Objektauftreten die Ereignisse geladen wird.  
  
 `wMajor`  
 Die Hauptversion der Typbibliothek.  Der Standardwert ist 0.  
  
 `wMinor`  
 Die Nebenversion der Typbibliothek.  Der Standardwert ist 0.  
  
 `tihclass`  
 Die Klasse verwendet, um die Typinformationen für `T` zu verwalten.  Der Standardwert ist eine Klasse Typ `CComTypeInfoHolder`; Sie können jedoch diesen Vorlagenparameter überschreiben, indem Sie eine Klasse anderen Typ als `CComTypeInfoHolder` bereitstellen.  
  
## Mitglieder  
  
### Öffentliche Typedefs  
  
|Name|Description|  
|----------|-----------------|  
|[IDispEventImpl::\_tihclass](../../atl/reference/idispeventimpl-class.md)|Die Klasse verwendet, um die Typinformationen zu verwalten.  Standardmäßig `CComTypeInfoHolder`.|  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[IDispEventImpl::IDispEventImpl](../Topic/IDispEventImpl::IDispEventImpl.md)|Der \-Konstruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[IDispEventImpl::GetFuncInfoFromId](../Topic/IDispEventImpl::GetFuncInfoFromId.md)|Errichtet den Funktionsindex für den angegebenen Dispatchbezeichner.|  
|[IDispEventImpl::GetIDsOfNames](../Topic/IDispEventImpl::GetIDsOfNames.md)|Ordnet einen einzelnen Member und einen optionalen Satz Argumentnamen in einen geeigneten Satz von ganzzahligen DISPID zu.|  
|[IDispEventImpl::GetTypeInfo](../Topic/IDispEventImpl::GetTypeInfo.md)|Ruft die Typinformationen für ein Objekt ab.|  
|[IDispEventImpl::GetTypeInfoCount](../Topic/IDispEventImpl::GetTypeInfoCount.md)|Ruft die Anzahl der Typinformationsschnittstellen ab.|  
|[IDispEventImpl::GetUserDefinedType](../Topic/IDispEventImpl::GetUserDefinedType.md)|Ruft den grundlegenden Typ eines benutzerdefinierten Typs ab.|  
  
## Hinweise  
 `IDispEventImpl` stellt eine Methode der Implementierung einer Ereignisdispatchschnittstelle bereit, ohne Sie veranlassen, Implementierungscode für jede Methode\/Ereignis für diese Schnittstelle zu erzeugen.  `IDispEventImpl` stellt Implementierungen der `IDispatch`\-Methoden.  Sie müssen nur Implementierungen für die Ereignisse stellen, dass Sie bei der Behandlung von Interesse sind.  
  
 `IDispEventImpl` funktioniert in Verbindung mit [Ereignissenkenzuordnung](../Topic/BEGIN_SINK_MAP.md) in der Klasse, um Ereignisse der entsprechenden Handlerfunktion weiterzuleiten.  Um diese Klasse verwenden:  
  
 Fügen Sie ein [SINK\_ENTRY](../Topic/SINK_ENTRY.md) oder [SINK\_ENTRY\_EX](../Topic/SINK_ENTRY_EX.md)\-Makro der Ereignissenkenzuordnung für jedes Ereignis auf jedem Objekt hinzu, das Sie behandeln möchten.  Wenn Sie `IDispEventImpl` als Basisklasse zusammengesetztes Steuerelement verwenden, können Sie [AtlAdviseSinkMap](../Topic/AtlAdviseSinkMap.md) aufrufen, um die Verbindung mit den Ereignisquellen für alle Senkenzuordnung der Einträge im Ereignishandler zu erstellen und zu unterbrechen.  In anderen Argumenten oder für größere Kontrolle, Aufruf [DispEventAdvise](../Topic/IDispEventSimpleImpl::DispEventAdvise.md), um die Verbindung zwischen dem Quellobjekt und der Basisklasse herzustellen.  Aufruf [DispEventUnadvise](../Topic/IDispEventSimpleImpl::DispEventUnadvise.md), um die Verbindung zu unterbrechen.  
  
 Sie müssen von `IDispEventImpl` \(mithilfe eines eindeutigen Werts für `nID`\) für jedes Objekt abgeleitet sind, für das Sie Ereignisse behandeln müssen.  Sie können die Basisklasse wiederverwenden, indem Sie für ein Quellobjekt einem anderen Quellobjekt dann abratend von abmelden, aber die maximale Anzahl von Quellobjekte verwendet, die durch ein einzelnes Objekt gleichzeitig verarbeitet werden können, wird durch die Anzahl der `IDispEventImpl` Basisklassen beschränkt.  
  
 `IDispEventImpl` stellt die gleiche Funktionalität wie, [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md), außer es Typinformation über die Schnittstelle aus einer Typbibliothek anstatt abruft, sie aufweisen, als Zeiger auf eine Struktur [\_ATL\_FUNC\_INFORMATION](../../atl/reference/atl-func-info-structure.md) angegeben hat.  Verwenden Sie `IDispEventSimpleImpl`, wenn Sie keine Typbibliothek verfügen, die Ereignisschnittstelle beschreibt oder den Mehraufwand vermeiden möchten, der mit der Anwendung der Typbibliothek zugeordnet ist.  
  
> [!NOTE]
>  `IDispEventImpl` und `IDispEventSimpleImpl` stellen ihre eigene Implementierung von **IUnknown::QueryInterface**, jede `IDispEventImpl` und `IDispEventSimpleImpl` Basisklasse aktiviert, die als separate COM\-Identität beim Zugriff auf den Klassenmember im wichtigsten COM\-Objekt noch ermöglichen fungiert.  
  
 Implementierung CEs ATL von ActiveX\-Ereignissenken unterstützt nur Rückgabewerte vom Typ void HRESULT oder aus den Ereignishandlermethoden; anderer Rückgabewert wird nicht unterstützt und sein Verhalten ist nicht definiert.  
  
 Weitere Informationen finden Sie unter [Unterstützung von IDispEventImpl](../../atl/supporting-idispeventimpl.md).  
  
## Vererbungshierarchie  
 `_IDispEvent`  
  
 `_IDispEventLocator`  
  
 [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)  
  
 `IDispEventImpl`  
  
## Anforderungen  
 **Header:**  möchten  
  
## Siehe auch  
 [\_ATL\_FUNC\_INFO Structure](../../atl/reference/atl-func-info-structure.md)   
 [IDispatchImpl Class](../../atl/reference/idispatchimpl-class.md)   
 [IDispEventSimpleImpl Class](../../atl/reference/idispeventsimpleimpl-class.md)   
 [SINK\_ENTRY](../Topic/SINK_ENTRY.md)   
 [SINK\_ENTRY\_EX](../Topic/SINK_ENTRY_EX.md)   
 [SINK\_ENTRY\_INFO](../Topic/SINK_ENTRY_INFO.md)   
 [Class Overview](../../atl/atl-class-overview.md)