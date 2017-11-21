---
title: Range_adapter (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::range_adapter
dev_langs: C++
helpviewer_keywords: range_adapter class [STL/CLR]
ms.assetid: 3fbe2a65-1216-46a0-a182-422816b80cfb
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5455c1912b3108291f530ee9488a4e0078ba39a2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="rangeadapter-stlclr"></a>range_adapter (STL/CLR)
Eine Vorlagenklasse, die ein Paar von Iteratoren umschließt, mit denen mehrere Basisklassenbibliothek (Base Class Library, BCL)-Schnittstellen implementieren. Sie verwenden die Range_adapter einen STL/CLR-Bereich bearbeiten, als handele es sich um eine BCL-Auflistung.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<typename Iter>  
    ref class range_adapter  
        :   public  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<Value>,  
        System::Collections::Generic::ICollection<Value>  
    { ..... };  
```  
  
#### <a name="parameters"></a>Parameter  
 iter  
 Der Typ, der die umschlossenen Iteratoren zugeordnet wird.  
  
## <a name="members"></a>Mitglieder  
  
|Memberfunktion|Beschreibung|  
|---------------------|-----------------|  
|[range_adapter::range_adapter (STL/CLR)](../dotnet/range-adapter-range-adapter-stl-clr.md)|Erstellt ein Adapterobjekt.|  
  
|Operator|Beschreibung|  
|--------------|-----------------|  
|[range_adapter::operator= (STL/CLR)](../dotnet/range-adapter-operator-assign-stl-clr.md)|Ersetzt den gespeicherten Iterator-Paar.|  
  
## <a name="interfaces"></a>Schnittstellen  
  
|Schnittstelle|Beschreibung|  
|---------------|-----------------|  
|<xref:System.Collections.IEnumerable>|Durchlaufen Elemente in der Auflistung ein.|  
|<xref:System.Collections.ICollection>|Verwaltet eine Gruppe von Elementen an.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Durchläuft typisierter Elemente in der Auflistung...|  
|<xref:System.Collections.Generic.ICollection%601>|Verwaltet eine Gruppe von typisierten Elementen an.|  
  
## <a name="remarks"></a>Hinweise  
 Die Range_adapter speichert ein Paar von Iteratoren, die wiederum eine Sequenz von Elementen zu begrenzen. Das Objekt implementiert vier BCL-Schnittstellen, mit die die Elemente in Reihenfolge durchlaufen können. STL/CLR-Bereiche, ähnlich wie BCL Container bearbeiten, verwenden Sie diese Vorlagenklasse.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext-Adapter >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Collection_adapter (STL/CLR)](../dotnet/collection-adapter-stl-clr.md)   
 [make_collection (STL/CLR)](../dotnet/make-collection-stl-clr.md)