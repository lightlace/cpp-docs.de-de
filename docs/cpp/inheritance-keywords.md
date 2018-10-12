---
title: Vererbungsschlüsselwörter | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __multiple_inheritance
- __single_inheritance_cpp
- __virtual_inheritance_cpp
- __virtual_inheritance
- __multiple_inheritance_cpp
- __single_inheritance
dev_langs:
- C++
helpviewer_keywords:
- __single_inheritance keyword [C++]
- declaring derived classes [C++]
- keywords [C++], inheritance keywords
- __multiple_inheritance keyword [C++]
- __virtual_inheritance keyword [C++]
- inheritance, declaring derived classes
- derived classes [C++], declaring
- inheritance, keywords
ms.assetid: bb810f56-7720-4fea-b8b6-9499edd141df
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f4b3703d0bd4556090c08a874bce362120817397
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2018
ms.locfileid: "49161800"
---
# <a name="inheritance-keywords"></a>Vererbungsschlüsselwörter

**Microsoft-spezifisch**

```
class [__single_inheritance] class-name;
class [__multiple_inheritance] class-name;
class [__virtual_inheritance] class-name;
```

Dabei gilt:

*Klassennamen*<br/>
Der Name der zu deklarierenden Klasse.

C++ ermöglicht es Ihnen, vor der Definition der Klasse einen Zeiger auf einen Klassenmember zu deklarieren. Zum Beispiel:

```cpp
class S;
int S::*p;
```

Im obigen Code `p` wird als Zeiger auf den ganzzahligen Member der Klasse s deklariert Allerdings `class S` wurde noch nicht in diesem Code definiert wurde es nur deklariert wurde. Wenn der Compiler einen solchen Zeiger erkennt, muss er eine allgemeine Darstellung des Zeigers erzeugen. Die Größe der Darstellung ist vom angegebenen Vererbungsmodell abhängig. Es gibt vier Möglichkeiten, ein Vererbungsmodell für den Compiler anzugeben:

- In der IDE unter **Pointer-to-Member-Darstellung**

- In der Befehlszeile unter Verwendung der [/vmg](../build/reference/vmb-vmg-representation-method.md) wechseln

- Mithilfe der [Pointers_to_members](../preprocessor/pointers-to-members.md) Pragma

- Mithilfe der vererbungs-Schlüsselwörter **__single_inheritance**, **__multiple_inheritance**, und **__virtual_inheritance**. Dieses Verfahren steuert das Vererbungsmodell auf Basis einer einzelnen Klasse.

    > [!NOTE]
    >  Wenn Sie stets einen Zeiger auf einen Member einer Klasse deklarieren, nachdem Sie die Klasse definiert haben, ist es nicht erforderlich, eine dieser Optionen zu verwenden.

Das Deklarieren eines Zeigers auf einen Member einer Klasse vor der Klassendefinition wirkt sich auf die Größe und die Geschwindigkeit der erstellten ausführbaren Datei aus. Je komplexer die von einer Klasse genutzte Vererbung ist, desto größer sind die Byteanzahl, die für die Darstellung eines Zeigers auf einen Member der Klasse erforderlich ist, und der für die Interpretation des Zeigers erforderliche Code. Die einfache Vererbung ist am wenigsten komplex und die virtuelle Vererbung ist die komplexeste Vererbung.

Wenn das obige Beispiel so geändert wird:

```cpp
class __single_inheritance S;
int S::*p;
```

Unabhängig von Befehlszeilenoptionen oder Pragmas verwenden Zeiger auf Member von `class S` die kleinstmögliche Darstellung.

> [!NOTE]
>  Dieselbe Vorwärtsdeklaration einer pointer-to-member-Klassendarstellung sollte in jeder Übersetzungseinheit auftreten, die Zeiger auf Member dieser Klasse deklariert. Die Deklaration sollte vor der pointer-to-member-Deklaration erfolgen.

Für die Kompatibilität mit früheren Versionen **_single_inheritance**, **_multiple_inheritance**, und **_virtual_inheritance** sind Synonyme für **__ Single_inheritance**, **__multiple_inheritance**, und **__virtual_inheritance** , wenn Compileroption [/Za \(Sprache deaktivieren Extensions)](../build/reference/za-ze-disable-language-extensions.md) angegeben ist.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Schlüsselwörter](../cpp/keywords-cpp.md)