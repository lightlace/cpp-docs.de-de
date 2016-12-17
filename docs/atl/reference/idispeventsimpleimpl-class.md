---
title: "IDispEventSimpleImpl Class"
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
  - "IDispEventSimpleImpl"
  - "ATL::IDispEventSimpleImpl"
  - "ATL.IDispEventSimpleImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDispEventSimpleImpl class"
ms.assetid: 971d82b7-a921-47fa-a4d8-909bed377ab0
caps.latest.revision: 27
caps.handback.revision: "15"
ms.author: "mblome"
manager: "ghogen"
---
# IDispEventSimpleImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt die Implementierungen der `IDispatch`\-Methoden bereit, ohne Typinformationen aus einer Typbibliothek abzurufen.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausführen.  
  
## Syntax  
  
```  
  
      template <  
UINT nID,  
class T,  
const IID* pdiid  
>  
class ATL_NO_VTABLE IDispEventSimpleImpl :  
public _IDispEventLocator<nID, pdiid>  
```  
  
#### Parameter  
 `nID`  
 Ein eindeutiger Bezeichner für das Quellobjekt.  Wenn `IDispEventSimpleImpl` die Basisklasse für ein zusammengesetztes Steuerelement ist, verwenden Sie das Ressourcen\-ID des gewünschten enthaltenden Steuerelements für diesen Parameter.  In anderen Fällen verwenden Sie eine beliebige positive ganze Zahl.  
  
 `T`  
 Die Klasse des Benutzers, die von `IDispEventSimpleImpl` abgeleitet wird.  
  
 `pdiid`  
 Der Zeiger auf IID der Ereignisdispatchschnittstelle implementiert von dieser Klasse.  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[IDispEventSimpleImpl::Advise](../Topic/IDispEventSimpleImpl::Advise.md)|Richtet eine Verbindung mit der Standardereignisquelle ein.|  
|[IDispEventSimpleImpl::DispEventAdvise](../Topic/IDispEventSimpleImpl::DispEventAdvise.md)|Richtet eine Verbindung mit der Ereignisquelle ein.|  
|[IDispEventSimpleImpl::DispEventUnadvise](../Topic/IDispEventSimpleImpl::DispEventUnadvise.md)|Unterteilt die Verbindung mit der Ereignisquelle.|  
|[IDispEventSimpleImpl::GetIDsOfNames](../Topic/IDispEventSimpleImpl::GetIDsOfNames.md)|Gibt **E\_NOTIMPL**.|  
|[IDispEventSimpleImpl::GetTypeInfo](../Topic/IDispEventSimpleImpl::GetTypeInfo.md)|Gibt **E\_NOTIMPL**.|  
|[IDispEventSimpleImpl::GetTypeInfoCount](../Topic/IDispEventSimpleImpl::GetTypeInfoCount.md)|Gibt **E\_NOTIMPL**.|  
|[IDispEventSimpleImpl::Invoke](../Topic/IDispEventSimpleImpl::Invoke.md)|Ruft die Ereignishandler aufgelistete im \- Senkenzuordnung auf.|  
|[IDispEventSimpleImpl::Unadvise](../Topic/IDispEventSimpleImpl::Unadvise.md)|Unterteilt die Verbindung mit der Standardereignisquelle.|  
  
## Hinweise  
 `IDispEventSimpleImpl` stellt eine Methode der Implementierung einer Ereignisdispatchschnittstelle bereit, ohne Sie veranlassen, Implementierungscode für jede Methode\/Ereignis für diese Schnittstelle zu erzeugen.  `IDispEventSimpleImpl` stellt Implementierungen der `IDispatch`\-Methoden.  Sie müssen nur Implementierungen für die Ereignisse stellen, dass Sie bei der Behandlung von Interesse sind.  
  
 `IDispEventSimpleImpl` funktioniert in Verbindung mit [Ereignissenkenzuordnung](../Topic/BEGIN_SINK_MAP.md) in der Klasse, um Ereignisse der entsprechenden Handlerfunktion weiterzuleiten.  Um diese Klasse verwenden:  
  
-   Fügen Sie ein [SINK\_ENTRY\_INFORMATION](../Topic/SINK_ENTRY_INFO.md)\-Makro der Ereignissenkenzuordnung für jedes Ereignis auf jedem Objekt hinzu, das Sie behandeln möchten.  
  
-   Zubehörtypinformationen für jedes Ereignis durch Übergeben eines Zeigers auf eine [\_ATL\_FUNC\_INFORMATION](../../atl/reference/atl-func-info-structure.md)\-Struktur als Parameter zu jedem Eintrag.  Klicken Sie auf der `_ATL_FUNC_INFO.cc` x86\-Plattform muss der Wert CC\_CDECL mit dem Rückruffunktionsaufruf von werden von \_\_stdcall sein.  
  
-   Rufen Sie [DispEventAdvise](../Topic/IDispEventSimpleImpl::DispEventAdvise.md) auf, um die Verbindung zwischen dem Quellobjekt und der Basisklasse herzustellen.  
  
-   Aufruf [DispEventUnadvise](../Topic/IDispEventSimpleImpl::DispEventUnadvise.md), um die Verbindung zu unterbrechen.  
  
 Sie müssen von `IDispEventSimpleImpl` \(mithilfe eines eindeutigen Werts für `nID`\) für jedes Objekt abgeleitet sind, für das Sie Ereignisse behandeln müssen.  Sie können die Basisklasse wiederverwenden, indem Sie für ein Quellobjekt einem anderen Quellobjekt dann abratend von abmelden, aber die maximale Anzahl von Quellobjekte verwendet, die durch ein einzelnes Objekt gleichzeitig verarbeitet werden können, wird durch die Anzahl der `IDispEventSimpleImpl` Basisklassen beschränkt.  
  
 **IDispEventSimplImpl** stellt die gleiche Funktionalität wie [IDispEventImpl](../../atl/reference/idispeventimpl-class.md) bereit, außer es keine Typinformationen über die Schnittstelle aus einer Typbibliothek abruft.  Die Assistenten generieren den Code, der nur auf `IDispEventImpl` basiert, aber Sie können `IDispEventSimpleImpl` verwenden, indem Sie den Code manuell hinzufügen.  Verwenden Sie `IDispEventSimpleImpl`, wenn Sie keine Typbibliothek verfügen, die Ereignisschnittstelle beschreibt oder den Mehraufwand vermeiden möchten, der mit der Anwendung der Typbibliothek zugeordnet ist.  
  
> [!NOTE]
>  `IDispEventImpl` und `IDispEventSimpleImpl` stellen ihre eigene Implementierung von **IUnknown::QueryInterface**, jede `IDispEventImpl` oder `IDispEventSimpleImpl` Basisklasse aktiviert, die als separate COM\-Identität beim Zugriff auf den Klassenmember im wichtigsten COM\-Objekt noch ermöglichen fungiert.  
  
 Implementierung CEs ATL von ActiveX\-Ereignissenken unterstützt nur Rückgabewerte vom Typ void HRESULT oder aus den Ereignishandlermethoden; anderer Rückgabewert wird nicht unterstützt und sein Verhalten ist nicht definiert.  
  
 Weitere Informationen finden Sie unter [Unterstützung von IDispEventImpl](../../atl/supporting-idispeventimpl.md).  
  
## Vererbungshierarchie  
 `_IDispEvent`  
  
 `_IDispEventLocator`  
  
 `IDispEventSimpleImpl`  
  
## Anforderungen  
 **Header:**  möchten  
  
## Siehe auch  
 [\_ATL\_FUNC\_INFO Structure](../../atl/reference/atl-func-info-structure.md)   
 [IDispatchImpl Class](../../atl/reference/idispatchimpl-class.md)   
 [IDispEventImpl Class](../../atl/reference/idispeventimpl-class.md)   
 [SINK\_ENTRY\_INFO](../Topic/SINK_ENTRY_INFO.md)   
 [Class Overview](../../atl/atl-class-overview.md)