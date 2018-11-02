---
title: Ändern eines Symbols oder Symbolnamens (ID)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.symbol.changing
helpviewer_keywords:
- symbol names
- symbols [C++], names
ms.assetid: 26541832-8dba-4177-b642-e08f94502ea7
ms.openlocfilehash: 98df98a2ed466066d9f0d32d6686e55e75280167
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50487398"
---
# <a name="changing-a-symbol-or-symbol-name-id"></a>Ändern eines Symbols oder Symbolnamens (ID)

Wenn Sie eine neue Ressource oder ein Ressourcenobjekt erstellen, weist die Entwicklungsumgebung einen standardmäßigen Symbolnamen zu, beispielsweise IDD_DIALOG1. Sie können die [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window) um den standardmäßigen Symbolnamen zu ändern oder den Namen eines beliebigen bereits mit einer Ressource verknüpften Symbols zu ändern.

### <a name="to-change-a-resources-symbol-name"></a>So ändern Sie den Symbolname einer Ressource

1. In [Ressourcenansicht](../windows/resource-view-window.md), wählen Sie die Ressource.

   > [!NOTE]
   > Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

2. In der **Eigenschaften** Fenster, geben Sie einen neuen Symbolnamen ein, oder wählen Sie aus der Liste der vorhandenen Symbole im der **ID** Feld.

   Wenn Sie einen neuen Symbolnamen eingeben, wird diesem automatisch ein Wert zugewiesen.

Sie können die [Ressourcensymbole (Dialogfeld)](../windows/resource-symbols-dialog-box.md) so ändern Sie die Namen der derzeit nicht auf eine Ressource zugewiesenen Symbole. Weitere Informationen finden Sie unter [ändern nicht zugewiesener Symbole](../windows/changing-unassigned-symbols.md).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Beschränkungen bei Symbolnamen](../windows/symbol-name-restrictions.md)<br/>
[Vordefinierte Symbol-IDs](../windows/predefined-symbol-ids.md)