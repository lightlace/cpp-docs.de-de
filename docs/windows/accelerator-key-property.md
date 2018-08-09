---
title: Accelerator-Schlüsseleigenschaft | Microsoft-Dokumentation
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
ms.openlocfilehash: 36884376e5ff31754e4c53ef6602f6bfd129f4a4
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39650442"
---
# <a name="accelerator-key-property"></a>Eigenschaft "Taste" von Zugriffstasten
Die folgenden sind Einträge zulässig für die Eigenschaft "Schlüssel" in der tastenkombinationstabelle:  
  
-   Eine ganze Zahl zwischen 0 und 255 im Dezimalformat. Der Wert bestimmt, ob der Wert als ASCII oder ANSI, wie folgt behandelt wird:  
  
    -   Einstellige Zahlen werden immer als der entsprechende Schlüssel und nicht als ASCII oder ANSI-Werte interpretiert.  
  
    -   Werte von 1 bis 26, wenn Nullen vorangestellt werden als interpretiert ^ A bis ^ Z, steht für den ASCII-Wert, der den Buchstaben des Alphabets, wenn Sie mit gedrückt der **STRG** -Taste gedrückt gehalten.  
  
    -   Werte von 27-32 werden immer als drei Ziffern bestehenden Dezimalwerte 027 bis 032 interpretiert.  
  
    -   Werte von 033 bis 255, 0 vorangestellt oder nicht als ANSI-Werte interpretiert werden.  
  
-   Ein einzelnes Zeichen der Tastatur. Großbuchstaben von A - Z oder die Ziffern 0 – 9 können entweder ASCII- oder den virtuellen Schlüsselwerte; Alle anderen Zeichen ist ASCII nur an.  
  
-   Ein einzelnes Zeichen der Tastatur im Bereich von A - Z (nur Großbuchstaben), ein Caretzeichen (^) vorangestellt (z. B. ^ C). Dies gibt den ASCII-Wert des Schlüssels, wenn es gedrückt wird, mit der **STRG** -Taste gedrückt gehalten.  
  
    > [!NOTE]
    >  Wenn Sie einen ASCII-Wert eingeben, sind die Modifizierer-Optionen beschränkt. Ist der einzige Steuerelement verfügbare Schlüssel für die Verwendung der **Alt** Schlüssel.  
  
-   Alle gültigen virtuellen Tastenbezeichner. Die Dropdownliste im Feld in der tastenkombinationstabelle enthält eine Liste der standardmäßigen virtuellen Schlüsselbezeichner.  
  
    > [!TIP]
    >  Eine weitere Möglichkeit zum Definieren einer Zugriffstaste wird mit der rechten Maustaste einen oder mehrere Einträge in der Zugriffstastentabelle, wählen **Nächste Taste** aus dem Kontextmenü, und drücken Sie dann eine der Tasten bzw. Tastenkombinationen auf der Tastatur. Die **Nächste Taste** Befehl steht auch auf die **bearbeiten** Menü.  
  
## <a name="requirements"></a>Anforderungen  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Zugriffstasteneigenschaften](../windows/setting-accelerator-properties.md)   
 [Bearbeiten in einer Zugriffstastentabelle](../windows/editing-in-an-accelerator-table.md)   
 [Zugriffstasten-Editor](../windows/accelerator-editor.md)