---
title: Accelerator Schlüsseleigenschaft | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Key property
ms.assetid: d1570cd9-b414-4cd6-96bd-47c38281eaca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e4fc56384d666026f4cc7e21f9d8af9347046fd1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33857206"
---
# <a name="accelerator-key-property"></a>Eigenschaft "Taste" von Zugriffstasten
Die folgenden sind rechtliche Einträge für die Eigenschaft "Taste" in der Zugriffstastentabelle:  
  
-   Eine ganze Zahl zwischen 0 und 255 im Dezimalformat. Der Wert bestimmt, ob der Wert als ASCII oder ANSI, wie folgt behandelt wird:  
  
    -   Einstellige Zahlen werden immer als die entsprechenden Schlüssel anstatt als ASCII oder ANSI-Werte interpretiert.  
  
    -   Werte von 1 bis 26, wenn Nullen vorangestellt sind als interpretiert ^ A bis ^ Z, das den ASCII-Wert, der die Buchstaben des Alphabets, wenn Sie mit gedrückter STRG-Taste gedrückt darstellt.  
  
    -   Werte von 27 bis 32 werden immer als drei Ziffern Dezimalwerte 027 bis 032 interpretiert.  
  
    -   Werte von 033 bis 255, 0 vorangestellt oder nicht als ANSI-Werte interpretiert werden.  
  
-   Ein einzelnes Zeichen der Tastatur. Großbuchstaben von A - Z, oder die Zahlen 0 - 9 ASCII- oder virtuellen Schlüsselwerte sein; Alle anderen Zeichen ist nur ASCII.  
  
-   Ein einzelnes Zeichen der Tastatur aus dem Bereich A - Z (nur Großbuchstaben), ein Caretzeichen (^) vorangestellt (z. B. ^ C). Dies gibt den ASCII-Wert des Schlüssels, wenn sie mit gedrückter STRG-Taste gedrückt wird.  
  
    > [!NOTE]
    >  Wenn Sie einen ASCII-Wert eingeben, sind die Änderungsoptionen für die Eigenschaft beschränkt. Für die Verwendung der ALT-Taste wird nur STRG-Taste.  
  
-   Alle gültigen virtuellen Schlüsselbezeichner. Das Dropdownfeld Schlüssel in der Zugriffstastentabelle enthält eine Liste der standardmäßigen virtuellen Schlüsselbezeichner.  
  
    > [!TIP]
    >  Eine weitere Möglichkeit zum Definieren einer Zugriffstaste wird mit der rechten Maustaste einen oder mehrere Einträge in der Zugriffstastentabelle, wählen **Nächste Taste** aus dem Kontextmenü, und drücken Sie dann die Änderungen an den Schlüssel oder -Tastenkombinationen auf der Tastatur drücken. Die **Nächste Taste** Befehl steht auch auf die **bearbeiten** Menü.  
  
## <a name="requirements"></a>Anforderungen  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Zugriffstasteneigenschaften](../windows/setting-accelerator-properties.md)   
 [Bearbeiten in einer Zugriffstastentabelle](../windows/editing-in-an-accelerator-table.md)   
 [Zugriffstasten-Editor](../windows/accelerator-editor.md)