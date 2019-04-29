---
title: 'MFC-ActiveX-Steuerelemente: Eigenschaften'
ms.date: 11/04/2016
helpviewer_keywords:
- properties [MFC], ActiveX controls
- MFC ActiveX controls [MFC], properties
- properties [MFC]
ms.assetid: b678a53c-0d9e-476f-8aa0-23b80baaba46
ms.openlocfilehash: 5e01854e7ae7acdc33275351d0d26a76dfeabc9b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62324323"
---
# <a name="mfc-activex-controls-properties"></a>MFC-ActiveX-Steuerelemente: Eigenschaften

Ein ActiveX-Steuerelement löst Ereignisse für die Kommunikation mit dem Steuerelementcontainer aus. Im Gegenzug werden in der Container, Methoden und Eigenschaften für die Kommunikation mit dem Steuerelement verwendet. Methoden und Eigenschaften sind ähnlich und Zweck, Memberfunktionen und Membervariablen einer C++-Klasse. Eigenschaften sind Datenmember, der das ActiveX-Steuerelement, die an einen beliebigen Container verfügbar gemacht werden. Eigenschaften bieten eine Schnittstelle für Anwendungen, die ActiveX-Steuerelemente, z. B. Benutzeroberflächenautomatisierungs-Clients und ActiveX-Steuerelemente enthalten.

Eigenschaften werden auch als Attribute bezeichnet.

Weitere Informationen zu Methoden der ActiveX-Steuerelements, finden Sie im Artikel [MFC-ActiveX-Steuerelemente: Methoden](../mfc/mfc-activex-controls-methods.md).

ActiveX-Steuerelemente können sowohl Kurs- und benutzerdefinierten Methoden und Eigenschaften implementieren. Klasse `COleControl` stellt eine Implementierung für die vordefinierten Eigenschaften. (Eine vollständige Liste der vordefinierten Eigenschaften, finden Sie im Artikel [MFC-ActiveX-Steuerelemente: Hinzufügen von vordefinierten Eigenschaften](../mfc/mfc-activex-controls-adding-stock-properties.md).) Benutzerdefinierte Eigenschaften, die vom Entwickler definierten fügen Sie spezielle Funktionen zu einem ActiveX-Steuerelement hinzu. Weitere Informationen finden Sie unter [MFC-ActiveX-Steuerelemente: Hinzufügen von benutzerdefinierten Eigenschaften](../mfc/mfc-activex-controls-adding-custom-properties.md).

Sowohl benutzerdefinierte als auch vordefinierte Eigenschaften, wie Methoden, werden durch einen Mechanismus, der eine Dispatchzuordnung besteht, die Eigenschaften und Methoden und vorhandenen Memberfunktionen von behandelt unterstützt die `COleControl` Klasse. Darüber hinaus können diese Eigenschaften über Parameter verfügen, die der Entwickler verwendet, um zusätzliche Informationen für das Steuerelement zu übergeben.

In den folgenden Artikeln besprechen Sie Eigenschaften von ActiveX-Steuerelemente im Detail:

- [MFC-ActiveX-Steuerelemente: Hinzufügen von vordefinierten Eigenschaften](../mfc/mfc-activex-controls-adding-stock-properties.md)

- [MFC-ActiveX-Steuerelemente: Hinzufügen von benutzerdefinierten Eigenschaften](../mfc/mfc-activex-controls-adding-custom-properties.md)

- [MFC-ActiveX-Steuerelemente: Weiterführende Eigenschaftenimplementierung](../mfc/mfc-activex-controls-advanced-property-implementation.md)

- [MFC-ActiveX-Steuerelemente: Zugreifen auf Umgebungseigenschaften](../mfc/mfc-activex-controls-accessing-ambient-properties.md)

## <a name="see-also"></a>Siehe auch

[MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)
