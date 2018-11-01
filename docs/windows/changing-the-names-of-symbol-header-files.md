---
title: Ändern der Namen von Symbolheaderdateien
ms.date: 11/04/2016
f1_keywords:
- vc.editors.symbol.changing.header
helpviewer_keywords:
- resource files [C++], multiple
- Resource Includes dialog box [C++]
- symbol header files [C++], changing names
- symbols [C++], symbol header files
- Resource.h
ms.assetid: b948284a-7899-402e-ab12-9f2c8480ca9d
ms.openlocfilehash: 4d9aa350d0f680e975c68bf46ac066072df044cb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50432333"
---
# <a name="changing-the-names-of-symbol-header-files"></a>Ändern der Namen von Symbolheaderdateien

Normalerweise alle Symboldefinitionen, die in gespeichert werden `Resource.h`. Jedoch müssen Sie den Namen dieser Includedatei möglicherweise ändern, sodass Sie z. B. mit mehr als eine Ressourcendatei im selben Verzeichnis arbeiten können.

### <a name="to-change-the-name-of-the-resource-symbol-header-file"></a>So ändern Sie den Namen den Symbolheaderdatei für die Ressource

1. In [Ressourcenansicht](../windows/resource-view-window.md)mit der rechten Maustaste auf die RC-Datei, und wählen Sie [Ressourcenincludes](../windows/resource-includes-dialog-box.md) aus dem Kontextmenü.

   > [!NOTE]
   > Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

2. In der **Symbolheaderdatei** geben den neuen Namen für die Include-Datei.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Anzeigen von Ressourcensymbolen](../windows/viewing-resource-symbols.md)<br/>
[Vordefinierte Symbol-IDs](../windows/predefined-symbol-ids.md)