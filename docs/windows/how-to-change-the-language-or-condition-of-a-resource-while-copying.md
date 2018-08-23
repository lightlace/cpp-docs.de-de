---
title: 'Vorgehensweise: Ändern der Sprache oder Bedingung einer Ressource während des Kopierens | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.resvw.resource.changing
dev_langs:
- C++
helpviewer_keywords:
- Language property
- condition property of resource
ms.assetid: 8f622ab0-bac2-468f-ae70-78911afc4759
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 508655dbfeb2d06d936d2b73d5435cf04c860f4b
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42598933"
---
# <a name="how-to-change-the-language-or-condition-of-a-resource-while-copying"></a>Gewusst wie: Ändern der Sprache oder Bedingung einer Ressource während des Kopierens

Beim Kopieren in eine Ressource können Sie ihre Sprachen- und/oder Bedingungseigenschaft ändern.

- Die Ressourcensprache ermittelt lediglich die Sprache für die Ressource. Dies dient der [FindResource](http://msdn.microsoft.com/library/windows/desktop/ms648042) können Sie die Ressource zu identifizieren, für die Sie suchen. (Ressourcen können für jede Sprache Unterschiede aufweisen, die nicht mit dem Text zusammenhängen, z. B. Tastenkombinationen, die nur auf einer japanischen Tastatur funktionieren, oder eine Bitmap, die nur für Builds in Chinesisch gilt usw.)

- Die Bedingung einer Ressource stellt ein definiertes Symbol dar, das eine Bedingung angibt, unter der diese bestimmte Ressourcenkopie zu verwenden ist.

Sprache und Bedingung einer Ressource werden im Arbeitsbereichsfenster nach dem Ressourcennamen in Klammern angezeigt. In diesem Beispiel verwendet die Ressource mit dem Namen „IDD_AboutBox“ Finnisch als Sprache und „XX33“ als Bedingung.

```cpp
IDD_AboutBox (Finnish - XX33)  
```

### <a name="to-copy-an-existing-resource-and-change-its-language-or-condition"></a>So kopieren Sie eine vorhandene Ressource und ändern die Sprache oder Bedingung

1. In der RC-Datei oder in der [Ressourcenansicht](../windows/resource-view-window.md) Fenster mit der rechten Maustaste in der Ressource, die Sie kopieren möchten.

2. Wählen Sie **Kopie einfügen** aus dem Kontextmenü.

3. In der **Ressourcenkopie** Dialogfeld:

   - Für die **Sprache** Listenfeld, wählen Sie die Sprache.

   - In der **Bedingung** geben die Bedingung.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Vorgehensweise: Kopieren von Ressourcen](../windows/how-to-copy-resources.md)  
[Ressourcendateien](../windows/resource-files-visual-studio.md)  
[Ressourcen-Editor](../windows/resource-editors.md)