---
title: "IDataObjectImpl Class"
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
  - "IDataObjectImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "data transfer [C++]"
  - "data transfer [C++], Uniform Data Transfer"
  - "IDataObject, ATL-Implementierung"
  - "IDataObjectImpl class"
ms.assetid: b680f0f7-7795-40a1-a0f6-f48768201c89
caps.latest.revision: 20
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# IDataObjectImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt Methoden für die Unterstützung der einheitlichen Datenübertragung und Verwalten von Verbindungen bereit.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausführen.  
  
## Syntax  
  
```  
  
      template< class   
      T  
      >  
class IDataObjectImpl  
```  
  
#### Parameter  
 `T`  
 Die Klasse, die von abgeleitet `IDataObjectImpl`.  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[IDataObjectImpl::DAdvise](../Topic/IDataObjectImpl::DAdvise.md)|Richtet eine Verbindung zwischen dem Datenobjekt und einer Advise\-Senke ein.  Dadurch können die Advise\-Senke, um Benachrichtigungen von Änderungen im Objekt zu empfangen.|  
|[IDataObjectImpl::DUnadvise](../Topic/IDataObjectImpl::DUnadvise.md)|Beendet eine Verbindung, die zuvor durch `DAdvise` eingerichtet wird.|  
|[IDataObjectImpl::EnumDAdvise](../Topic/IDataObjectImpl::EnumDAdvise.md)|Erstellt einen Enumerator, um die aktuellen Advise\-Verbindungen zu durchlaufen.|  
|[IDataObjectImpl::EnumFormatEtc](../Topic/IDataObjectImpl::EnumFormatEtc.md)|Erstellt einen Enumerator, um die **FORMATETC**\-Strukturen zu durchlaufen, die durch das Datenobjekt unterstützt werden.  Die ATL\-Implementierung gibt **E\_NOTIMPL** zurück.|  
|[IDataObjectImpl::FireDataChange](../Topic/IDataObjectImpl::FireDataChange.md)|Sendet eine Änderungsbenachrichtigung zurück zu jeder Advise\-Senke.|  
|[IDataObjectImpl::GetCanonicalFormatEtc](../Topic/IDataObjectImpl::GetCanonicalFormatEtc.md)|Ruft eine logisch entsprechende **FORMATETC**\-Struktur bis eine ab, die komplexer ist.  Die ATL\-Implementierung gibt **E\_NOTIMPL** zurück.|  
|[IDataObjectImpl::GetData](../Topic/IDataObjectImpl::GetData.md)|Überträgt Daten vom Datenobjekt zum Client.  Die Daten werden in einer **FORMATETC**\-Struktur beschrieben und werden durch eine **STGMEDIUM**\-Struktur übertragen.|  
|[IDataObjectImpl::GetDataHere](../Topic/IDataObjectImpl::GetDataHere.md)|Vergleichbar mit, außer `GetData` der Client die **STGMEDIUM**\-Struktur zugeordnet werden muss.  Die ATL\-Implementierung gibt **E\_NOTIMPL** zurück.|  
|[IDataObjectImpl::QueryGetData](../Topic/IDataObjectImpl::QueryGetData.md)|Bestimmt, ob das Datenobjekt eine bestimmte **FORMATETC**\-Struktur für die Übertragung von Daten unterstützt.  Die ATL\-Implementierung gibt **E\_NOTIMPL** zurück.|  
|[IDataObjectImpl::SetData](../Topic/IDataObjectImpl::SetData.md)|Überträgt Daten vom Client zum Datenobjekt.  Die ATL\-Implementierung gibt **E\_NOTIMPL** zurück.|  
  
## Hinweise  
 Die [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421)\-Schnittstelle stellt Methoden zum Unterstützungsuniform\-Datenübertragung bereit.  `IDataObject` verwendet die Standardformatstrukturen [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) und [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812), um Daten abzurufen und zu speichern.  
  
 `IDataObject` verwaltet auch Verbindungen zu den Advise\-Senken zu den Handledatenänderungsbenachrichtigungen.  Damit der Client Datenänderungsbenachrichtigungen vom Datenobjekt, dem Client muss die [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513)\-Schnittstelle in einem Objekt implementieren empfängt, das eine Advise\-Senke aufgerufen wird.  Wenn der Client dann **IDataObject::DAdvise** aufruft, wird eine Verbindung zwischen dem Datenobjekt und der Advise\-Senke festgelegt.  
  
 \- Klasse `IDataObjectImpl` stellt eine Standardimplementierung von `IDataObject` und implementiert **IUnknown**, indem Informationen zum Sicherungsgerät in Debugbuilds sendet.  
  
 **Verwandte Elemente** [ATL\-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL\-Projekts](../../atl/reference/creating-an-atl-project.md)  
  
## Vererbungshierarchie  
 `IDataObject`  
  
 `IDataObjectImpl`  
  
## Anforderungen  
 **Header:**  atlctl.h  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)