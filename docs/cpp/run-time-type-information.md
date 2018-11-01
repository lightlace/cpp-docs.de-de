---
title: Laufzeit-Typeninformation | Microsoft-Dokumentation
ms.custom: index-page
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- RTTI compiler option
- run-time type information
- run time, type checking
- type information, run-time type checking
- run-time checks, type checking
ms.assetid: becbd0e5-0439-4c61-854f-8a74f7160c54
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9f9ce0094bce1f8e7590cef0cbe3bfe85f35158d
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50056060"
---
# <a name="run-time-type-information"></a>Laufzeit-Typinformationen

Laufzeittypinformationen (Run-Time Type Information, RTTI) sind ein Mechanismus, mit dem der Typ eines Objekts während der Programmausführung bestimmt werden kann. Laufzeittypinformationen wurden zur Programmiersprache C++ hinzugefügt, da viele Anbieter von Klassenbibliotheken diese Funktion selbst implementiert haben. Dies verursachte Inkompatibilitäten zwischen Bibliotheken. Deshalb wurde es offensichtlich, dass eine Unterstützung der Laufzeittypinformationen auf Sprachebene erforderlich war.

Aus Gründen der Übersichtlichkeit wird die Erläuterung der Laufzeittypinformationen nahezu ausschließlich auf Zeiger beschränkt. Jedoch gelten die erläuterten Konzepte auch für Verweise.

Es gibt drei primäre Sprachelemente von C++ zur Ausführung von Laufzeittypinformationen:

- Die [Dynamic_cast](../cpp/dynamic-cast-operator.md) Operator.

   Wird zur Konvertierung von polymorphen Typen verwendet.

- Die [Typeid](../cpp/typeid-operator.md) Operator.

   Wird zum Kennzeichnen des genauen Typ eines Objekts verwendet.

- Die [Type_info](../cpp/type-info-class.md) Klasse.

   Verwendet, um die Typinformationen, die zurückgegeben werden, von aufzunehmen der **Typeid** Operator.

## <a name="see-also"></a>Siehe auch

[Umwandlung](../cpp/casting.md)