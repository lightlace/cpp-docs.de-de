---
title: Reinterpret_cast-Operator | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- reinterpret_cast_cpp
dev_langs:
- C++
helpviewer_keywords:
- reinterpret_cast keyword [C++]
ms.assetid: eb3283c7-7f88-467e-affd-407d37b46d6c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 27522cb4d3bb15912b7988e0152a121616480330
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39464833"
---
# <a name="reinterpretcast-operator"></a>reinterpret_cast-Operator
Ermöglicht, dass ein beliebiger Zeiger in einen anderen Zeigertyp konvertiert wird. Ermöglicht es außerdem, einen beliebigen ganzzahligen Typ in einen beliebigen Zeigertyp und umgekehrt zu konvertieren.  
  
## <a name="syntax"></a>Syntax  
  
```  
reinterpret_cast < type-id > ( expression )  
```  
  
## <a name="remarks"></a>Hinweise  
 Falsche Verwendung der **"reinterpret_cast"** Operator kann ganz einfach unsicheren sein. Sofern nicht die gewünschte Konvertierung grundsätzlich auf niedriger Ebene stattfindet, sollten Sie einen der anderen Umwandlungsoperatoren verwenden.  
  
 Die **"reinterpret_cast"** -Operator kann z. B. für Konvertierungen verwendet werden `char*` zu `int*`, oder `One_class*` zu `Unrelated_class*`, die grundsätzlich unsicher sind.  
  
 Das Ergebnis einer **"reinterpret_cast"** nicht für etwas anderes als die Umwandlung zurück in den ursprünglichen Typ sicher verwendet werden. Andere Verwendungsmöglichkeiten sind bestenfalls nicht portierbar.  
  
 Die **"reinterpret_cast"** Operator nicht umwandeln der **const**, **flüchtige**, oder **__unaligned** Attribute. Finden Sie unter [Const_cast-Operator](../cpp/const-cast-operator.md) Informationen zum Entfernen dieser Attribute.  
  
 Die **"reinterpret_cast"** -Operator konvertiert einen null-Zeiger-Wert, der null-Zeigerwert des Zieltyps.  
  
 Eine praktische Verwendung von **"reinterpret_cast"** befindet sich in eine Hash-Funktion, welche Karten einen Wert in einen Index in einer Weise, dass zwei verschiedene Werte am Ende selten sich mit demselben Index.  
  
```cpp 
#include <iostream>  
using namespace std;  
  
// Returns a hash code based on an address  
unsigned short Hash( void *p ) {  
   unsigned int val = reinterpret_cast<unsigned int>( p );  
   return ( unsigned short )( val ^ (val >> 16));  
}  
  
using namespace std;  
int main() {  
   int a[20];  
   for ( int i = 0; i < 20; i++ )  
      cout << Hash( a + i ) << endl;  
}  
  
Output:   
64641  
64645  
64889  
64893  
64881  
64885  
64873  
64877  
64865  
64869  
64857  
64861  
64849  
64853  
64841  
64845  
64833  
64837  
64825  
64829  
```  
  
 Die **"reinterpret_cast"** kann der Zeiger als ganzzahliger Typ behandelt werden. Das Ergebnis ist dann eine Bitverschiebung oder ein XOR-Vorgang, um einen eindeutigen Index zu erstellen (eindeutig mit hoher Wahrscheinlichkeit). Der Index wird dann von einer standardmäßigen Umwandlung im C-Format in den Rückgabetyp der Funktion abgeschnitten.  
  
## <a name="see-also"></a>Siehe auch  
 [Umwandlungsoperatoren](../cpp/casting-operators.md)   
 [Schlüsselwörter](../cpp/keywords-cpp.md)