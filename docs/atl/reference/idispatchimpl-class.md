---
title: "IDispatchImpl Class"
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
  - "IDispatchImpl"
  - "ATL.IDispatchImpl"
  - "ATL::IDispatchImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "duale Schnittstellen, Klassen"
  - "Unterstützung für IDispatch-Klasse in ATL"
  - "IDispatchImpl-Klasse"
ms.assetid: 8108eb36-1228-4127-a203-3ab5ba488892
caps.latest.revision: 27
caps.handback.revision: "15"
ms.author: "mblome"
manager: "ghogen"
---
# IDispatchImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt eine Standardimplementierung für den `IDispatch` Teil einer dualen Schnittstelle bereit.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausführen.  
  
## Syntax  
  
```  
template<  
   class T,  
   const IID* piid= &__uuidof(T),  
   const GUID* plibid = &CAtlModule::m_libid,  
   WORD wMajor = 1,  
   WORD wMinor = 0,  
   class tihclass = CComTypeInfoHolder   
>   
class ATL_NO_VTABLE IDispatchImpl :  
   public T  
```  
  
#### Parameter  
 \[in\] `T`  
 Eine duale Schnittstelle.  
  
 \[in\] `piid`  
 Ein Zeiger auf IID von `T`.  
  
 \[in\] `plibid`  
 Ein Zeiger auf LIBID der Typbibliothek, die Informationen über die Schnittstelle enthält.  Standardmäßig wird die Typbibliothek auf Serverebene übergeben.  
  
 \[in\] `wMajor`  
 Die Hauptversion der Typbibliothek.  Der Standardwert ist 1.  
  
 \[in\] `wMinor`  
 Die Nebenversion der Typbibliothek.  Der Standardwert ist 0.  
  
 \[in\] `tihclass`  
 Die Klasse verwendet, um die Typinformationen für `T` zu verwalten.  Der Standardwert ist `CComTypeInfoHolder`.  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[IDispatchImpl::IDispatchImpl](../Topic/IDispatchImpl::IDispatchImpl.md)|Der \-Konstruktor.  Ruft `AddRef` auf der geschützten Membervariable auf, die die Typinformationen für die duale Schnittstelle verwaltet.  Der Destruktor ruft `Release` auf.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[IDispatchImpl::GetIDsOfNames](../Topic/IDispatchImpl::GetIDsOfNames.md)|Ordnet eine Reihe von Namen einer entsprechenden Reihe von Dispatchbezeichnern zu.|  
|[IDispatchImpl::GetTypeInfo](../Topic/IDispatchImpl::GetTypeInfo.md)|Ruft die Typinformationen für die duale Schnittstelle ab.|  
|[IDispatchImpl::GetTypeInfoCount](../Topic/IDispatchImpl::GetTypeInfoCount.md)|Bestimmt, ob die Typinformationen gibt, die für die duale Schnittstelle verfügbar sind.|  
|[IDispatchImpl::Invoke](../Topic/IDispatchImpl::Invoke.md)|Bietet Zugriff auf Methoden und Eigenschaften, die von der duale Schnittstelle verfügbar gemacht werden.|  
  
## Hinweise  
 `IDispatchImpl` stellt eine Standardimplementierung für den `IDispatch` Teil einer dualen Schnittstelle in einem Objekt bereit.  Eine duale Schnittstelle abgeleitet von `IDispatch` und verwendet nur Automatisierung\-kompatible Typen.  Wie eine Dispatchschnittstelle unterstützt eine duale Schnittstelle und späte Bindung frühe Bindung; unterstützt jedoch auch eine duale Schnittstelle auch \- Bindung.  
  
 Im folgenden Beispiel wird eine typische Implementierung von `IDispatchImpl` veranschaulicht.  
  
 [!CODE [NVC_ATL_COM#47](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_COM#47)]  
  
 Standardmäßig sucht die `IDispatchImpl`\-Klasse oben die Typinformationen nach `T` in der Registrierung.  Um eine nicht registrierte Schnittstelle implementieren, können Sie die Klasse verwenden `IDispatchImpl` ohne auf die Registrierung zuzugreifen indem Sie eine vordefinierte Versionsnummer verwenden.  Wenn Sie ein Objekt erstellen, das `IDispatchImpl` 0xFFFF als Wert für `wMajor` und 0xFFFF als Wert für `wMinor` verfügt, ruft die `IDispatchImpl`\-Klasse die Typbibliothek der DLL\-Datei anstelle der Registrierung ab.  
  
 `IDispatchImpl` enthält einen statischen Member des Typs `CComTypeInfoHolder`, der die Typinformationen für die duale Schnittstelle verwaltet.  Wenn Sie mehrere Objekte verfügen, die dieselbe duale Schnittstelle implementieren, nur eine Instanz von `CComTypeInfoHolder` verwendet wird.  
  
## Vererbungshierarchie  
 `T`  
  
 `IDispatchImpl`  
  
## Anforderungen  
 **Header:** möchten  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)