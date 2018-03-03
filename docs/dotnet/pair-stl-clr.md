---
title: Paar (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::pair
dev_langs:
- C++
helpviewer_keywords:
- pair class [STL/CLR]
ms.assetid: 3326b4d9-a52a-49e5-8103-9aa5e8b352de
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a8c4ae8ee9fbcfddd6009d4e91134d59a9a02cc9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="pair-stlclr"></a>pair (STL/CLR)
Die Vorlagenklasse beschreibt ein Objekt, das ein Wertepaar umschließt.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<typename Value1,  
    typename Value2>  
    ref class pair;  
```  
  
#### <a name="parameters"></a>Parameter  
 Wert1  
 Der Typ des ersten einem Wrapper versehene Wert.  
  
 Value2  
 Der Typ des zweiten einem Wrapper versehene Wert.  
  
## <a name="members"></a>Member  
  
|Typdefinition|Beschreibung|  
|---------------------|-----------------|  
|[pair::first_type (STL/CLR)](../dotnet/pair-first-type-stl-clr.md)|Der Typ des ersten umschlossene Werts.|  
|[pair::second_type (STL/CLR)](../dotnet/pair-second-type-stl-clr.md)|Der Typ des umschlossenen Sekundenwert.|  
  
|Member-Objekt|Beschreibung|  
|-------------------|-----------------|  
|[pair::first (STL/CLR)](../dotnet/pair-first-stl-clr.md)|Der erste gespeicherte Wert.|  
|[pair::second (STL/CLR)](../dotnet/pair-second-stl-clr.md)|Der zweite gespeicherte Wert.|  
  
|Memberfunktion|Beschreibung|  
|---------------------|-----------------|  
|[pair::pair (STL/CLR)](../dotnet/pair-pair-stl-clr.md)|Erstellt ein paarobjekt.|  
|[pair::swap (STL/CLR)](../dotnet/pair-swap-stl-clr.md)|Vertauscht den Inhalt von zwei Wertepaaren.|  
  
|Operator|Beschreibung|  
|--------------|-----------------|  
|[pair::operator= (STL/CLR)](../dotnet/pair-operator-assign-stl-clr.md)|Ersetzt das gespeicherte Paar von Werten an.|  
  
## <a name="remarks"></a>Hinweise  
 Das Objekt speichert ein Paar von Werten. Um zwei Werte zu einem einzigen Objekt kombiniert werden. verwenden Sie diese Vorlagenklasse. Beachten Sie, dass `cliext::pair` (hier beschriebenen) speichert nur von verwalteten Typen; verwenden Sie zum Speichern von ein Paar von nicht verwalteten Typen `std::pair`, die im deklariert `<utility>`.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext-Hilfsprogramm >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [make_pair (STL/CLR)](../dotnet/make-pair-stl-clr.md)