---
title: Make_public | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.make_public
- make_public_CPP
dev_langs:
- C++
helpviewer_keywords:
- pragmas, make_public
- make_public pragma
ms.assetid: c3665f4d-268a-4932-9661-c37c8ae6a341
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 27db5ac934973178e2485327090ed70f994becec
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="makepublic"></a>make_public
Gibt an, dass für einen systemeigenen Typ der öffentliche Assemblyzugriff gewährt wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
#pragma make_public(type)  
```  
  
### <a name="parameters"></a>Parameter  
 `type` ist der Name des Typs, der den öffentlichen Assemblyzugriff aufweisen soll.  
  
## <a name="remarks"></a>Hinweise  
`make_public` ist sinnvoll, wenn der systemeigene Typ, auf den Sie verweisen möchten, aus einer H-Datei stammt, die Sie nicht ändern können. Soll der systemeigene Typ in der Signatur einer öffentlichen Funktion in einem Typ mit öffentlicher Assemblysichtbarkeit verwendet werden, muss der systemeigene Typ auch über den öffentlichen Assemblyzugriff verfügen, sonst gibt der Compiler eine Warnung aus.  
  
`make_public` muss im globalen Bereich angegeben werden und ist nur wirksam von diesem Deklarationspunkt bis zum Ende der Quellcodedatei.  
  
Der systemeigene Typ kann implizit oder explizit privat sein; finden Sie unter [Typsichtbarkeit](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) für Weitere Informationen.  
  
## <a name="example"></a>Beispiel  
Beim folgenden Beispiel handelt es sich um die Inhalte einer H-Datei, welche die Definitionen für zwei systemeigene Strukturen enthält.  
  
```cpp  
// make_public_pragma.h  
struct Native_Struct_1 { int i; };  
struct Native_Struct_2 { int i; };  
```  
  
## <a name="example"></a>Beispiel  
Das folgende Codebeispiel verwendet die Headerdatei und veranschaulicht, dass der Compiler – sofern die systemeigenen Strukturen nicht explizit unter Verwendung von `make_public` als öffentlich gekennzeichnet sind – eine Warnung generiert, wenn Sie versuchen, die systemeigenen Strukturen in der Signatur einer öffentlicher Funktion in einem öffentlichen verwalteten Typ zu verwenden.  
  
```cpp  
// make_public_pragma.cpp  
// compile with: /c /clr /W1  
#pragma warning (default : 4692)  
#include "make_public_pragma.h"  
#pragma make_public(Native_Struct_1)  
  
public ref struct A {  
   void Test(Native_Struct_1 u) {u.i = 0;}   // OK  
   void Test(Native_Struct_2 u) {u.i = 0;}   // C4692  
};  
```  
  
## <a name="see-also"></a>Siehe auch  
[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)