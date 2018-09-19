---
title: Ressource Ressourcensymbol-Dialogfelds (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.resourcesymbols
dev_langs:
- C++
helpviewer_keywords:
- New Symbol dialog box [C++]
- Resource Symbols dialog box [C++]
- Change Symbol dialog box [C++]
ms.assetid: 9706cde3-1f48-4fcd-bedb-2b03b455e3c1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 09d34d0247f7fd039bca3ea9b643802856734926
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45719302"
---
# <a name="resource-symbols-dialog-box-c"></a>Ressource Ressourcensymbole (Dialogfeld) (C++)

Die **Ressourcensymbole** C++-Dialogfeld können Sie neue Ressourcensymbole hinzufügen, ändern die Symbole, die angezeigt werden, oder fahren Sie mit der Position im Quellcode, in denen ein Symbol verwendet wird.

- **Name**

   Zeigt den Namen des Symbols an. Weitere Informationen finden Sie unter [Beschränkungen bei Symbolnamen](../windows/symbol-name-restrictions.md).

- **Wert**

   Zeigt den numerischen Wert des Symbols an. Weitere Informationen finden Sie unter [Beschränkungen für Symbolwerte](../windows/symbol-value-restrictions.md).

- **In Verwendung**

   Bei Auswahl dieser Option wird angegeben, dass das Symbol von einer oder mehreren Ressourcen verwendet wird. Die Ressourcen sind im Feld „Verwendet von aufgeführt“.

- **Schreibgeschützte Symbole anzeigen**

   Bei Auswahl dieser Option werden schreibgeschützte Ressourcen angezeigt. In der Standardeinstellung die **Ressourcensymbol** im Dialogfeld werden nur die änderbaren Ressourcen in Ihrer Ressourcenskriptdatei angezeigt, aber diese Option ausgewählt ist, werden änderbare Ressourcen fett und schreibgeschützte Ressourcen werden im nur-Text angezeigt.

- **Verwendet von**

   Zeigt die Ressource bzw. Ressourcen an, in der/denen das in der Symbolliste markierte Symbol verwendet wird. Um in den Editor für eine bestimmte Ressource verschieben möchten, wählen Sie die Ressource in der **verwendet von** ein, und klicken Sie auf **Verwendung anzeigen**. Weitere Informationen finden Sie unter [Öffnen des Ressourcen-Editors für ein bestimmtes Symbol](../windows/opening-the-resource-editor-for-a-given-symbol.md).

- **Neu**

   Öffnet die **neues Symbol** Dialogfeld, das Ihnen ermöglicht, definieren den Namen und, falls erforderlich, einen Wert für einen neuen symbolischen Ressourcenbezeichner. Weitere Informationen finden Sie unter [Erstellen neuer Symbole](../windows/creating-new-symbols.md).

- **Änderung**

   Öffnet die **Symbol ändern** im Dialogfeld, in dem Sie den Namen oder Wert eines Symbols ändern kann. Wenn das Symbol für ein Steuerelement oder eine Ressource in Gebrauch ist, kann das Symbol nur im entsprechenden Ressourcen-Editor geändert werden. Weitere Informationen finden Sie unter [ändern nicht zugewiesener Symbole](../windows/changing-unassigned-symbols.md).

- **Verwendung anzeigen**

   Öffnet die Ressource, die das Symbol enthält, im entsprechenden Ressourcen-Editor. Weitere Informationen finden Sie unter [Öffnen des Ressourcen-Editors für ein bestimmtes Symbol](../windows/opening-the-resource-editor-for-a-given-symbol.md).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Anzeigen von Ressourcensymbolen](../windows/viewing-resource-symbols.md)