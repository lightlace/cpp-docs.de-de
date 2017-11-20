---
title: Noreturn | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: noreturn_cpp
dev_langs: C++
helpviewer_keywords:
- __declspec keyword [C++], noreturn
- noreturn __declspec keyword
ms.assetid: 9c6517e5-22d7-4051-9974-3d2200ae4d1d
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 91c6a7b38653a3bb0a86927ced602fd85ff29277
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="noreturn"></a>noreturn
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 Dieses `__declspec`-Attribut weist den Compiler an, dass keine Funktion zurückgegeben wird. Daher der Compiler weiß, dass der Code nach einem Aufruf einer **__declspec(noreturn)** Funktion ist nicht erreichbar.  
  
 Wenn der Compiler eine Funktion mit einem Kontrollpfad findet, die keinen Wert zurückgibt, wird eine Warnung (C4715) oder Fehlermeldung (C2202) generiert. Wenn der Kontrollpfad wegen einer Funktion nicht, die nie zurückgegeben erreichbar ist, können Sie **__declspec(noreturn)** um diese Warnung bzw. diesen Fehler zu verhindern.  
  
> [!NOTE]
>  Hinzufügen von **__declspec(noreturn)** an eine Funktion, der erwartet wird, zurückgegeben kann zu nicht definiertem Verhalten.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die **else** -Klausel keine return-Anweisung.  Deklarieren von `fatal` als **__declspec(noreturn)** vermeidet einen Fehler oder Warnung angezeigt.  
  
```  
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