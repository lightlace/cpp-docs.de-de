---
title: "Rahmenfensterstile (MFC)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "FWS_ADDTOTITLE"
  - "FWS_SNAPTOBARS"
  - "FWS_PREFIXTITLE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Rahmenfenster, Stile"
  - "FWS_ADDTOTITLE-Konstante"
  - "FWS_PREFIXTITLE-Konstante"
  - "FWS_SNAPTOBARS--Konstante"
  - "Stile, Fenster"
ms.assetid: d21f270e-a088-4962-a2ae-8c03334b5a06
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Rahmenfensterstile (MFC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

-   **FWS\_ADDTOTITLE** gibt Informationen an, um am Ende eines Rahmenfenstertitels anzufügen.  Beispiel "Microsoft zeichnen \- Zeichnungen in Document1".  Sie können Zeichenfolgen angeben, die in der Dokumentvorlagen\-Zeichenfolgenregisterkarte im Anwendungs\-Assistenten angezeigt werden.  Wenn Sie diese Option deaktivieren müssen, überschreiben Sie die `CWnd::PreCreateWindow`\-Memberfunktion.  
  
-   **FWS\_PREFIXTITLE** wird vor den Dokumentnamen der Anwendungsname in einem Rahmenfenstertitel an.  Durch "Dokument \- WordPad".  Sie können Zeichenfolgen angeben, die in der Dokumentvorlagen\-Zeichenfolgenregisterkarte im Anwendungs\-Assistenten angezeigt werden.  Wenn Sie diese Option deaktivieren müssen, überschreiben Sie die `CWnd::PreCreateWindow`\-Memberfunktion.  
  
-   **FWS\_SNAPTOBARS** Kontrollenskalieren des Rahmenfensters, das eine Steuerleiste enthält, in ein unverankertes Fenster statt auf einem Rahmenfenster angedockt ist.  Dieses Format skaliert das Fenster, um die Steuerleiste anzupassen.  
  
## Siehe auch  
 [Von MFC verwendete Stile](../../mfc/reference/styles-used-by-mfc.md)