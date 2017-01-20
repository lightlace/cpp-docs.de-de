---
title: "IProvideClassInfo2Impl Class"
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
  - "IProvideClassInfo2"
  - "ATL.IProvideClassInfo2Impl"
  - "IProvideClassInfo2Impl"
  - "ATL::IProvideClassInfo2Impl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "class information, ATL"
  - "IProvideClassInfo2 ATL implementation"
  - "IProvideClassInfo2Impl class"
ms.assetid: d74956e8-9c69-4cba-b99d-ca1ac031bb9d
caps.latest.revision: 20
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# IProvideClassInfo2Impl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt eine Standardimplementierung der [IProvideClassInfo](http://msdn.microsoft.com/library/windows/desktop/ms687303) und [IProvideClassInfo2](http://msdn.microsoft.com/library/windows/desktop/ms693764)\-Methoden.  
  
## Syntax  
  
```  
  
      template <  
   const CLSID* pcoclsid,  
   const IID* psrcid,  
   const GUID* plibid = &CAtlModule::m_libid,  
   WORD wMajor = 1,  
   WORD wMinor = 0,  
   class tihclass = CComTypeInfoHolder   
>  
class ATL_NO_VTABLE IProvideClassInfo2Impl :  
   public IProvideClassInfo2  
```  
  
#### Parameter  
 *pcoclsid*  
 Ein Zeiger auf den Bezeichner der Co\-Klassen.  
  
 *psrcid*  
 Ein Zeiger auf den Bezeichner für die standardmäßigen ausgehende Dispatchschnittstelle der Co\-Klassen.  
  
 `plibid`  
 Ein Zeiger auf LIBID der Typbibliothek, die Informationen über die Schnittstelle enthält.  Standardmäßig wird die Typbibliothek auf Serverebene übergeben.  
  
 `wMajor`  
 Die Hauptversion der Typbibliothek.  Der Standardwert ist 1.  
  
 `wMinor`  
 Die Nebenversion der Typbibliothek.  Der Standardwert ist 0.  
  
 `tihclass`  
 Die Klasse verwendet, um die Typinformationen der Co\-Klassen zu verwalten.  Der Standardwert ist `CComTypeInfoHolder`.  
  
## Mitglieder  
  
### Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[IProvideClassInfo2Impl::IProvideClassInfo2Impl](../Topic/IProvideClassInfo2Impl::IProvideClassInfo2Impl.md)|Konstruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[IProvideClassInfo2Impl::GetClassInfo](../Topic/IProvideClassInfo2Impl::GetClassInfo.md)|Ruft einen **ITypeInfo** Zeiger auf Typinformationen der Co\-Klassen ab.|  
|[IProvideClassInfo2Impl::GetGUID](../Topic/IProvideClassInfo2Impl::GetGUID.md)|Ruft die GUID für die ausgehende Dispatchschnittstelle des Objekts ab.|  
  
### Geschützte Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[IProvideClassInfo2Impl::\_tih](../Topic/IProvideClassInfo2Impl::_tih.md)|Verwaltet die Typinformationen für die Co\-Klasse.|  
  
## Hinweise  
 Die [IProvideClassInfo2](http://msdn.microsoft.com/library/windows/desktop/ms693764)\-Schnittstelle erweitert [IProvideClassInfo](http://msdn.microsoft.com/library/windows/desktop/ms687303), indem sie die `GetGUID`\-Methode hinzugefügt wird.  Diese Methode ermöglicht einem Client, um die Ausgangsschnittstelle IID eines Objekts für den Standardereignissatz abzurufen.  \- Klasse `IProvideClassInfo2Impl` stellt eine Standardimplementierung der **IProvideClassInfo** und `IProvideClassInfo2`\-Methoden.  
  
 `IProvideClassInfo2Impl` enthält einen statischen Member des Typs `CComTypeInfoHolder`, der die Typinformationen für die Co\-Klasse verwaltet.  
  
## Vererbungshierarchie  
 `IProvideClassInfo2`  
  
 `IProvideClassInfo2Impl`  
  
## Anforderungen  
 **Header:**  möchten  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)