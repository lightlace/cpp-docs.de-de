---
title: Noreturn | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- noreturn_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], noreturn
- noreturn __declspec keyword
ms.assetid: 9c6517e5-22d7-4051-9974-3d2200ae4d1d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 662ccef9f0acf1d73e8db51cc042c6f4d59d38bc
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39403387"
---
# <a name="noreturn"></a>noreturn
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 Dies **__declspec** Attribut weist den Compiler, dass keine Funktion zurückgegeben wird. Infolgedessen wird der Compiler weiß, dass der Code nach einem Aufruf einer **__declspec(noreturn)** Funktion ist nicht erreichbar.  
  
 Wenn der Compiler eine Funktion mit einem Kontrollpfad findet, die keinen Wert zurückgibt, wird eine Warnung (C4715) oder Fehlermeldung (C2202) generiert. Wenn der Kontrollpfad wegen einer Funktion nicht, die nie zurückgegeben erreichbar ist, können Sie **__declspec(noreturn)** um diese Warnung oder Fehler zu vermeiden.  
  
> [!NOTE]
>  Hinzufügen von **__declspec(noreturn)** an eine Funktion, die erwartet wird, zurückgeben können zu nicht definiertem Verhalten.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die **else** -Klausel keine return-Anweisung.  Deklarieren von `fatal` als **__declspec(noreturn)** vermeidet einen Fehler oder eine Warnmeldung angezeigt.  
  
```cpp 
// noreturn2.cpp  
__declspec(noreturn) extern void fatal () {}  
  
int main() {  
   if(1)  
     return 1;  
   else if(0)  
     return 0;  
   else  
     fatal();  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [__declspec](../cpp/declspec.md)   
 [Schlüsselwörter](../cpp/keywords-cpp.md)