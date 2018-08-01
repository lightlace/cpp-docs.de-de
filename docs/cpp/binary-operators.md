---
title: Binäre Operatoren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- member-selection operators [C++]
- operators [C++], binary
- binary operators [C++]
ms.assetid: c0e7fbff-bc87-4708-8333-504ac09ee83e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4b76250926ab89c14dfa26f0df3bb5571c1dae10
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408815"
---
# <a name="binary-operators"></a>Binäre Operatoren

Die folgende Tabelle zeigt eine Liste von Operatoren, die überladen werden können.

## <a name="redefinable-binary-operators"></a>Neu definierbare binäre Operatoren

|Operator|name|
|--------------|----------|
|**,**|Komma|
|**\!=**|Ungleichheit|
|**%**|Modulooperator|
|**%=**|Modulo/Zuweisung|
|**&**|Bitweises AND|
|**&&**|Logisches AND|
|**&=**|Bitweises AND/Zuweisung|
|**&#42;**|Multiplikation|
|**&#42;=**|Multiplikation/Zuweisung|
|**+**|Addition|
|**+=**|Addition/Zuweisung|
|**-**|Subtraktion|
|**-=**|Subtraktion/Zuweisung|
|**->**|Memberauswahl|
|**->&#42;**|Pointer-to-member-Auswahl|
|**/**|Division|
|**/=**|Division/Zuweisung|
|**<**|Kleiner als|
|**<<**|Nach links verschieben|
|**<<=**|Nach links verschieben/Zuweisung|
|**<=**|Kleiner oder gleich|
|**=**|Zuweisung|
|**==**|Gleichheit|
|**>**|Größer als|
|**>=**|Größer oder gleich|
|**>>**|Nach rechts verschieben|
|**>>=**|Nach rechts verschieben/Zuweisung|
|**^**|Exklusives OR|
|**^=**|Exklusives OR/Zuweisung|
|**&#124;**|Bitweises inklusives OR|
|**&#124;=**|Bitweises inklusives OR/Zuweisung|
|**&#124;&#124;**|Logisches OR|

Um eine binäre Operatorfunktion als nicht statischen Member zu deklarieren, muss sie im folgenden Format deklariert werden:

> *ret-Type* **Operator** *Op* **(** *Arg* **)**

in denen *ret-Type* ist der Rückgabetyp, *Op* ist einer der in der obigen Tabelle aufgeführten Operatoren und *Arg* ist ein Argument eines beliebigen Typs.

Um eine binäre Operatorfunktion als globale Funktion zu deklarieren, muss sie im folgenden Format deklariert werden:

> *ret-Type* **Operator** *Op* **(** _arg1_**,** _arg2_ **)**

in denen *ret-Type* und *Op* sind für Member-Operatorfunktionen beschrieben und *arg1* und *arg2* sind Argumente. Mindestens eines der Argumente muss ein Klassentyp sein.

> [!NOTE]
> Es gibt keine Einschränkung für die Rückgabetypen der binären Operatoren. Die meisten benutzerdefinierten binären Operatoren geben jedoch entweder einen Klassentyp oder einen Verweis auf einen Klassentyp zurück.

## <a name="see-also"></a>Siehe auch
 [Operatorüberladung](../cpp/operator-overloading.md)