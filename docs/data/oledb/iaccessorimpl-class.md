---
title: "IAccessorImpl-Klasse"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "IAccessorImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IAccessorImpl-Klasse"
ms.assetid: 768606da-8b71-417c-a62c-88069ce7730d
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# IAccessorImpl-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt eine Implementierung der [IAccessor](https://msdn.microsoft.com/en-us/library/ms719672.aspx)\-Schnittstelle bereit.  
  
## Syntax  
  
```  
template <  
   class T,   
   class BindType = ATLBINDINGS,   
   class BindingVector = CAtlMap <   
      HACCESSOR hAccessor,   
      BindType* pBindingsStructure   
   >   
>  
class ATL_NO_VTABLE IAccessorImpl : public IAccessorImplBase<BindType>  
```  
  
#### Parameter  
 `T`  
 die Rowset\- oder Befehlsobjektklasse.  
  
 `BindType`  
 Speichereinheit für Bindungsinformationen Informationen.  Der Standardwert ist die **ATLBINDINGS**\-Struktur \(siehe atldb.h\).  
  
 `BindingVector`  
 Speichereinheit von Spalteninformationen.  Der Standardwert ist [CAtlMap](../../atl/reference/catlmap-class.md), in dem das ein Schlüsselelement **HACCESSOR**\-Wert ist und das Wertelement ein Zeiger auf eine Struktur ist `BindType`.  
  
## Member  
  
### Methoden  
  
|||  
|-|-|  
|[IAccessorImpl](../../data/oledb/iaccessorimpl-class.md)|Der \-Konstruktor.|  
  
### Schnittstellenmethoden  
  
|||  
|-|-|  
|[AddRefAccessor](../../data/oledb/iaccessorimpl-addrefaccessor.md)|Fügt einem vorhandenen Accessor einen Verweiszähler hinzu.|  
|[CreateAccessor](../../data/oledb/iaccessorimpl-createaccessor.md)|Erstellt einen Accessor aus einem Satz von Bindungen.|  
|[GetBindings](../../data/oledb/iaccessorimpl-getbindings.md)|Gibt die Bindungen in einem Accessor zurück.|  
|[ReleaseAccessor](../../data/oledb/iaccessorimpl-releaseaccessor.md)|Gibt einen Accessor frei.|  
  
## Hinweise  
 Dies ist auf Rowsets und Befehlen erforderlich.  OLE DB benötigt Anbieter, **HACCESSOR** zu implementieren, das einen Tag auf einem Array [DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx)\-Strukturen ist.  **HACCESSOR**s, das von `IAccessorImpl` bereitgestellt wird, sind der Adressen `BindType`\-Strukturen.  Standardmäßig wird `BindType` als **ATLBINDINGS** in der Vorlagendefinition `IAccessorImpl` definiert.  `BindType` stellt einen Mechanismus, der von `IAccessorImpl` verwendet wird, um die Anzahl der Elemente in den **DBBINDING** Array nachzuverfolgen sowie einem Verweiszähler und Accessorflags.  
  
## Anforderungen  
 **Header:**  atldb.h  
  
## Siehe auch  
 [OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)