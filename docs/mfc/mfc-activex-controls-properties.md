---
title: 'MFC-ActiveX-Steuerelemente: Eigenschaften | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- properties [MFC], ActiveX controls
- MFC ActiveX controls [MFC], properties
- properties [MFC]
ms.assetid: b678a53c-0d9e-476f-8aa0-23b80baaba46
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ac9d9e4f5e7d777bd147ce36e970e7a30fd875b2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="mfc-activex-controls-properties"></a>MFC-ActiveX-Steuerelemente: Eigenschaften
Ein ActiveX-Steuerelement löst Ereignisse für die Kommunikation mit seinem Steuerelementcontainer. Der Container verwendet im Gegenzug Methoden und Eigenschaften für die Kommunikation mit dem Steuerelement. Methoden und Eigenschaften sind ähnlich und Zweck bzw. Memberfunktionen und Membervariablen einer C++-Klasse. Eigenschaften sind Datenmember des ActiveX-Steuerelements, die zu einem beliebigen Container verfügbar gemacht werden. Eigenschaften bieten eine Schnittstelle für Anwendungen, die ActiveX-Steuerelemente, z. B. Automatisierungsclients und ActiveX-Steuerelementcontainer enthalten.  
  
 Eigenschaften werden auch als Attribute bezeichnet.  
  
 Weitere Informationen zu ActiveX-Steuerelement-Methoden finden Sie im Artikel [MFC-ActiveX-Steuerelemente: Methoden](../mfc/mfc-activex-controls-methods.md).  
  
 ActiveX-Steuerelemente können sowohl Kurs- und benutzerdefinierten Methoden und Eigenschaften implementieren. Klasse `COleControl` stellt eine Implementierung für vordefinierte Eigenschaften bereit. (Eine vollständige Liste der vordefinierten Eigenschaften, finden Sie im Artikel [MFC-ActiveX-Steuerelemente: Hinzufügen von Basiseigenschaften](../mfc/mfc-activex-controls-adding-stock-properties.md).) Benutzerdefinierte Eigenschaften, die vom Entwickler definierten hinzugefügt ein ActiveX-Steuerelement spezielle Funktionen. Weitere Informationen finden Sie unter [MFC-ActiveX-Steuerelemente: Hinzufügen benutzerdefinierter Eigenschaften](../mfc/mfc-activex-controls-adding-custom-properties.md).  
  
 Benutzerdefinierte und vordefinierte Eigenschaften, wie die Methoden werden durch einen Mechanismus, der eine Dispatchzuordnung besteht, die Eigenschaften und Methoden sowie vorhandene Memberfunktionen der behandelt, unterstützt die `COleControl` Klasse. Darüber hinaus können diese Eigenschaften über Parameter verfügen, mit der Entwickler zusätzlichen Informationen an das Steuerelement übergeben.  
  
 In den folgenden Artikeln werden Eigenschaften für ActiveX-Steuerelement im Detail beschrieben:  
  
-   [MFC-ActiveX-Steuerelemente: Hinzufügen von vordefinierten Eigenschaften](../mfc/mfc-activex-controls-adding-stock-properties.md)  
  
-   [MFC-ActiveX-Steuerelemente: Hinzufügen von benutzerdefinierten Eigenschaften](../mfc/mfc-activex-controls-adding-custom-properties.md)  
  
-   [MFC-ActiveX-Steuerelemente: Weiterführende Eigenschaftenimplementierung](../mfc/mfc-activex-controls-advanced-property-implementation.md)  
  
-   [MFC-ActiveX-Steuerelemente: Zugreifen auf Umgebungseigenschaften](../mfc/mfc-activex-controls-accessing-ambient-properties.md)  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)

