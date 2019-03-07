---
title: Ressourcen-IDs (Symbole) (C++)
ms.date: 02/14/2019
f1_keywords:
- vc.editors.symbol.identifiers
helpviewer_keywords:
- symbols [C++], resource identifiers
- symbols [C++], creating
- resource symbols
- symbols [C++], editing
- resource editors [C++], resource symbols
ms.assetid: 8fccc09a-0237-4a65-b9c4-57d60c59e324
ms.openlocfilehash: 63971ba381394bcaf905d614496511b7aa0d01f3
ms.sourcegitcommit: b4645761ce5acf8c2fc7a662334dd5a471ea976d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2019
ms.locfileid: "57563315"
---
# <a name="resource-identifiers-symbols-c"></a>Ressourcen-IDs (Symbole) (C++)

Ein Symbol ist ein Ressourcenbezeichner (ID), der aus zwei Teilen besteht einen Symbolnamen (Textzeichenfolge), ein Symbolwert (Integer), z. B. zugeordnet:

```
IDC_EDITNAME = 5100
```

Symbolnamen werden meistens als Bezeichner bezeichnet.

Symbole bieten eine anschauliche Möglichkeit, auf Ressourcen und Objekte der Benutzeroberfläche zu verweisen, sowohl im Quellcode als auch bei der Arbeit im Ressourcen-Editor. Mithilfe des Dialogfelds [Ressourcensymbole](../windows/viewing-resource-symbols.md)können Symbole komfortabel an einem Ort angezeigt und bearbeitet werden.

In dem Maß, in dem Ihre Anwendung in Umfang und Komplexität wächst, wächst auch die Anzahl ihrer Ressourcen und Symbole. Das Nachverfolgen einer großen Zahl von Symbolen, die über verschiedene Dateien verteilt sind, kann schwierig sein. Die **Ressourcensymbole** Dialogfeld vereinfacht die symbolverwaltung, indem bietet ein zentrales Tool, mit denen:

- [Erstellen von Symbolen](../windows/creating-new-symbols.md)

- [Verwaltung von Symbolen](../windows/changing-a-symbol-or-symbol-name-id.md)

- [Anzeigen vordefinierter Symbol-IDs](../windows/predefined-symbol-ids.md)

Wenn Sie eine neue Ressource oder ein neues Ressourcenobjekt erstellen, stellt der [Ressourcen-Editor](../windows/resource-editors.md) einen Standardnamen für die Ressource bereit, z. B. `IDC_RADIO1`, und weist ihr einen Wert zu. Die name-plus-Wert-Definition befindet sich in der `Resource.h` Datei.

> [!NOTE]
> Wenn Sie Ressourcen oder Ressourcenobjekte aus einer RC-Datei in eine andere kopieren, ändert Visual C++ möglicherweise den Symbolwert der übertragenen Ressource, oder den Symbolnamen und den Wert, um Konflikte mit Symbolnamen oder Werten in der vorhandenen Datei zu vermeiden.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Arbeiten mit Ressourcendateien](../windows/working-with-resource-files.md)<br/>
[Ressourcendateien](../windows/resource-files-visual-studio.md)<br/>
[Ressourcen-Editor](../windows/resource-editors.md)<br/>