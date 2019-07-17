---
title: exception-Klasse
ms.date: 11/04/2016
f1_keywords:
- exception
helpviewer_keywords:
- exception class
ms.assetid: 4f181f67-5888-4b50-89a6-745091ffb2fe
ms.openlocfilehash: 90906469e923d29dd886930bd36944e4292bd9cd
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68246070"
---
# <a name="exception-class"></a>exception-Klasse

Die Klasse dient als Basisklasse für alle Ausnahmen, die durch spezifische Ausdrücke und die C++-Standardbibliothek ausgelöst werden.

## <a name="syntax"></a>Syntax

```cpp
class exception {
   public:
   exception();
   exception(const char* const &message);
   exception(const char* const &message, int);
   exception(const exception &right);
   exception& operator=(const exception &right);
   virtual ~exception();
   virtual const char *what() const;
};
```

## <a name="remarks"></a>Hinweise

Diese Basisklasse bildet den Stamm der Standard Ausnahmeklassen, die in [\<stdexcept>](../standard-library/stdexcept.md) definiert sind. Der Wert der C-Zeichenfolge, der durch `what` zurückgegeben wird, wird vom Standardkonstruktor nicht angegeben, kann aber von den Konstruktoren für bestimmte abgeleitete Klassen als durch die Implementierung definierte C-Zeichenfolge angegeben werden. Keine der Memberfunktionen löst irgendeine Ausnahme aus.

Die **Int** Parameter können Sie angeben, dass kein Speicher zugewiesen werden soll. Der Wert des der **Int** wird ignoriert.

> [!NOTE]
> Die Konstruktoren `exception(const char* const &message)` und `exception(const char* const &message, int)` sind Microsoft-Erweiterungen der C++-Standardbibliothek.

## <a name="example"></a>Beispiel

Beispiele für die Verwendung von Standard Ausnahmeklassen, die von der `exception`-Klasse erben, finden Sie in allen unter [ \<stdexcept >](../standard-library/stdexcept.md) definierten Klassen.
