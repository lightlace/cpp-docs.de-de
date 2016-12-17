---
title: "CMFCMaskedEdit Class"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CMFCMaskedEdit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCMaskedEdit class"
  - "CMFCMaskedEdit constructor"
ms.assetid: 13b1a645-2d5d-4c37-8599-16d5003f23a5
caps.latest.revision: 30
caps.handback.revision: "18"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCMaskedEdit Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CMFCMaskedEdit`\-Klasse unterstützt ein maskiertes Bearbeitungssteuerelement, das Benutzereingaben anhand einer Maske überprüft und die überprüften Ergebnisse anhand einer Vorlage anzeigt.  
  
## Syntax  
  
```  
class CMFCMaskedEdit : public CEdit  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|`CMFCMaskedEdit::CMFCMaskedEdit`|Standardkonstruktor.|  
|`CMFCMaskedEdit::~CMFCMaskedEdit`|Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCMaskedEdit::DisableMask](../Topic/CMFCMaskedEdit::DisableMask.md)|Deaktiviert, die Benutzereingaben überprüfen.|  
|[CMFCMaskedEdit::EnableGetMaskedCharsOnly](../Topic/CMFCMaskedEdit::EnableGetMaskedCharsOnly.md)|Gibt an, ob die `GetWindowText`\-Methode nur maskierte Zeichen abruft.|  
|[CMFCMaskedEdit::EnableMask](../Topic/CMFCMaskedEdit::EnableMask.md)|Initialisiert das maskierte Bearbeitungssteuerelement.|  
|[CMFCMaskedEdit::EnableSelectByGroup](../Topic/CMFCMaskedEdit::EnableSelectByGroup.md)|Gibt an, ob das Bearbeitungssteuerelement maskierte bestimmte Gruppen Benutzereingaben auswählt, oder alle Benutzereingaben an.|  
|[CMFCMaskedEdit::EnableSetMaskedCharsOnly](../Topic/CMFCMaskedEdit::EnableSetMaskedCharsOnly.md)|Gibt an, ob der Text für nur maskierte Zeichen überprüft wird, oder für die Ganzmaske an.|  
|`CMFCMaskedEdit::GetThisClass`|Wird vom Framework, um ein Zeiger auf [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)\-Objekt abzurufen, das diesem Klassentyp zugeordnet ist.|  
|[CMFCMaskedEdit::GetWindowText](../Topic/CMFCMaskedEdit::GetWindowText.md)|Retrieves überprüfte Text vom maskierten Bearbeitungssteuerelement.|  
|[CMFCMaskedEdit::SetValidChars](../Topic/CMFCMaskedEdit::SetValidChars.md)|Gibt eine Zeichenfolge mit gültigen Zeichen an, die der Benutzer eingeben kann.|  
|[CMFCMaskedEdit::SetWindowText](../Topic/CMFCMaskedEdit::SetWindowText.md)|Zeigt eine Eingabeaufforderung im maskierten Bearbeitungssteuerelement an.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCMaskedEdit::IsMaskedChar](../Topic/CMFCMaskedEdit::IsMaskedChar.md)|Aufgerufen durch das Framework, um das angegebene Zeichen für das entsprechende Maskenzeichen zu überprüfen.|  
  
## Hinweise  
 Führen Sie die folgenden Schritte aus, um das `CMFCMaskedEdit`\-Steuerelement in Ihrer Anwendung verwenden:  
  
 1.  Betten Sie ein `CMFCMaskedEdit`\-Objekt in die Fensterklasse ein.  
  
 2.  Rufen Sie die [CMFCMaskedEdit::EnableMask](../Topic/CMFCMaskedEdit::EnableMask.md)\-Methode auf, um die Maske anzugeben.  
  
 3.  Rufen Sie die [CMFCMaskedEdit::SetValidChars](../Topic/CMFCMaskedEdit::SetValidChars.md)\-Methode auf, um die Liste der gültigen Zeichen anzugeben.  
  
 4.  Rufen Sie die [CMFCMaskedEdit::SetWindowText](../Topic/CMFCMaskedEdit::SetWindowText.md)\-Methode auf, um den Standardtext für das Bearbeitungssteuerelement maskierte anzugeben.  
  
 5.  Rufen Sie die [CMFCMaskedEdit::GetWindowText](../Topic/CMFCMaskedEdit::GetWindowText.md)\-Methode auf, um den überprüften Text abzurufen.  
  
 Wenn Sie keine oder mehrere Methoden aufrufen, um die Maske, die gültigen Zeichen und den Standardtext zu initialisieren, verhält sich das maskierte Bearbeitungssteuerelement, wie das Standardbearbeitungssteuerelement verhält.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie eine Maske \(beispielsweise eine Telefonnummer\) durch wird die `EnableMask`\-Methode, um die Maske zu erstellen installiert, sodass das maskierte Bearbeitungssteuerelement, die `SetValidChars`\-Methode, um eine Zeichenfolge von gültigen Zeichen angeben, die der Benutzer eingeben kann, und `SetWindowText`\-Methode eine Eingabeaufforderung im maskierten Bearbeitungssteuerelement anzeigt.  Dieses Beispiel ist Teil [Neue Kontrollprobe](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_NewControls#11](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_NewControls#11)]  
[!CODE [NVC_MFC_NewControls#12](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_NewControls#12)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CEdit](../../mfc/reference/cedit-class.md)  
  
 [CMFCMaskedEdit](../../mfc/reference/cmfcmaskededit-class.md)  
  
## Anforderungen  
 **Header:** afxmaskededit.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CEdit Class](../../mfc/reference/cedit-class.md)