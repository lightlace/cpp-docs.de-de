---
title: "CBindStatusCallback Class"
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
  - "CBindStatusCallback"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "asynchronous data transfer [C++]"
  - "CBindStatusCallback class"
  - "data transfer [C++]"
  - "data transfer [C++], Asynchron"
ms.assetid: 0f5da276-6031-4418-b2a9-a4750ef29e77
caps.latest.revision: 22
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# CBindStatusCallback Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse implementiert die `IBindStatusCallback`\-Schnittstelle.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
      template <class   
      T  
      , int   
      nBindFlags  
      = BINDF_ASYNCHRONOUS |   
BINDF_ASYNCSTORAGE | BINDF_GETNEWESTVERSION | BINDF_NOWRITECACHE>  
class ATL_NO_VTABLE CBindStatusCallback : public CComObjectRootEx  
<T::_ThreadModel::ThreadModelNoCS>, public IBindStatusCallbackImpl<T>   
```  
  
#### Parameter  
 `T`  
 Die Klasse, die die Funktion enthält, als die Daten, die aufgerufen wird, empfangen wird.  
  
 *nBindFlags*  
 Gibt die Bindungsflags an, die von [GetBindInfo](../Topic/CBindStatusCallback::GetBindInfo.md) zurückgegeben werden.  Die Standardimplementierung legt die Bindung fest, um asynchron zu sein, wird die letzte Version der Daten und des Objekts ab und speichert nicht abgerufene Daten im Datenträgercache.  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CBindStatusCallback::CBindStatusCallback](../Topic/CBindStatusCallback::CBindStatusCallback.md)|Der \-Konstruktor.|  
|[CBindStatusCallback::~CBindStatusCallback](../Topic/CBindStatusCallback::~CBindStatusCallback.md)|Der Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CBindStatusCallback::Download](../Topic/CBindStatusCallback::Download.md)|Statische Methode, die den Herunterladen beginnt, ein `CBindStatusCallback`\-Objekt erstellt und `StartAsyncDownload` aufruft.|  
|[CBindStatusCallback::GetBindInfo](../Topic/CBindStatusCallback::GetBindInfo.md)|Aufgerufen von der asynchronen Moniker, um Informationen über den Typ der zu erstellenden Bindung anzufordern.|  
|[CBindStatusCallback::GetPriority](../Topic/CBindStatusCallback::GetPriority.md)|Aufgerufen von der asynchronen Moniker, um die Priorität des Bindevorgangs abzurufen.  Die ATL\-Implementierung gibt `E_NOTIMPL` zurück.|  
|[CBindStatusCallback::OnDataAvailable](../Topic/CBindStatusCallback::OnDataAvailable.md)|Aufgerufen, um Daten zu der Anwendung bereitzustellen, wie sie verfügbar ist.  Liest die Daten, ruft die Funktion übergeben ihr, um die Daten zu verwenden auf.|  
|[CBindStatusCallback::OnLowResource](../Topic/CBindStatusCallback::OnLowResource.md)|Aufgerufen, wenn Ressourcen niedrig.  Die ATL\-Implementierung gibt `S_OK` zurück.|  
|[CBindStatusCallback::OnObjectAvailable](../Topic/CBindStatusCallback::OnObjectAvailable.md)|Aufgerufen von der asynchronen Moniker, um einen Objektschnittstellenzeiger an die Anwendung zu übergeben.  Die ATL\-Implementierung gibt `S_OK` zurück.|  
|[CBindStatusCallback::OnProgress](../Topic/CBindStatusCallback::OnProgress.md)|Aufgerufen, um den Status eines Datendownloadingprozesses anzugeben.  Die ATL\-Implementierung gibt `S_OK` zurück.|  
|[CBindStatusCallback::OnStartBinding](../Topic/CBindStatusCallback::OnStartBinding.md)|Beim Binden aufgerufen, gestartet wird.|  
|[CBindStatusCallback::OnStopBinding](../Topic/CBindStatusCallback::OnStopBinding.md)|Aufgerufen, wenn die asynchrone Datenübertragung beendet wird.|  
|[CBindStatusCallback::StartAsyncDownload](../Topic/CBindStatusCallback::StartAsyncDownload.md)|Initialisiert die Bytes verfügbar und Bytes lesen auf null, erstellen ein PushTyp Streamobjekt aus einer URL und rufen `OnDataAvailable` auf jedes Mal, wenn Daten verfügbar sind.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CBindStatusCallback::m\_dwAvailableToRead](../Topic/CBindStatusCallback::m_dwAvailableToRead.md)|Zahl zu lesenden Bytes verfügbar.|  
|[CBindStatusCallback::m\_dwTotalRead](../Topic/CBindStatusCallback::m_dwTotalRead.md)|Gesamtzahl Bytelesen.|  
|[CBindStatusCallback::m\_pFunc](../Topic/CBindStatusCallback::m_pFunc.md)|Zeiger auf die Funktion aufgerufen, wenn Daten verfügbar sind.|  
|[CBindStatusCallback::m\_pT](../Topic/CBindStatusCallback::m_pT.md)|Zeiger auf das Objekt die asynchrone Datenübertragung angefordert.|  
|[CBindStatusCallback::m\_spBindCtx](../Topic/CBindStatusCallback::m_spBindCtx.md)|Zeiger auf die [IBindCtx](http://msdn.microsoft.com/library/windows/desktop/ms693755)\-Schnittstelle für den aktuellen Bindevorgang.|  
|[CBindStatusCallback::m\_spBinding](../Topic/CBindStatusCallback::m_spBinding.md)|Zeiger auf die `IBinding`\-Schnittstelle für den aktuellen Bindevorgang.|  
|[CBindStatusCallback::m\_spMoniker](../Topic/CBindStatusCallback::m_spMoniker.md)|Zeiger auf die [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705)\-Schnittstelle, damit die URL verwendet.|  
|[CBindStatusCallback::m\_spStream](../Topic/CBindStatusCallback::m_spStream.md)|Zeiger auf die [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034)\-Schnittstelle für die Datenübertragung.|  
  
## Hinweise  
 Die `CBindStatusCallback`\-Klasse implementiert die `IBindStatusCallback`\-Schnittstelle.  `IBindStatusCallback` muss von der Anwendung implementiert werden, damit sie Benachrichtigungen von einer asynchronen Datenübertragung empfangen.  Der asynchrone Moniker, der vom System bereitgestellt wird, verwendet `IBindStatusCallback`\-Methoden, um Informationen über die asynchrone Datenübertragung nach und aus dem Objekt zu senden und zu erhalten.  
  
 In der Regel wird das `CBindStatusCallback`\-Objekt mit einem bestimmten Bindevorgang zugeordnet.  Im Beispiel [ASYNC](../../top/visual-cpp-samples.md), beim Festlegen der URL\-Eigenschaft, dieser ein `CBindStatusCallback`\-Objekt im Aufruf von `Download` erstellen:  
  
 [!CODE [NVC_ATL_Windowing#86](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#86)]  
  
 Der asynchrone Moniker verwendet die Rückruffunktion `OnData`, um die Anwendung aufzurufen, wenn Daten verfügt.  Der asynchrone Moniker wird vom System bereitgestellt.  
  
## Vererbungshierarchie  
 `CComObjectRootBase`  
  
 `IBindStatusCallback`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `CBindStatusCallback`  
  
## Anforderungen  
 **Header:**  atlctl.h  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)