---
title: "CMFCPropertyPage Class"
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
  - "CMFCPropertyPage"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCPropertyPage class"
  - "CMFCPropertyPage::CreateObject method"
  - "CMFCPropertyPage::OnSetActive method"
  - "CMFCPropertyPage::PreTranslateMessage method"
ms.assetid: d279d7f2-2d81-418d-9f23-6147d6e8df09
caps.latest.revision: 30
caps.handback.revision: "18"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCPropertyPage Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CMFCPropertyPage`\-Klasse unterstützt die Anzeige von Popupmenüs auf einer Eigenschaftenseite.  
  
## Syntax  
  
```  
class CMFCPropertyPage : public CPropertyPage  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCPropertyPage::CMFCPropertyPage](../Topic/CMFCPropertyPage::CMFCPropertyPage.md)|Erstellt ein `CMFCPropertyPage`\-Objekt.|  
|`CMFCPropertyPage::~CMFCPropertyPage`|Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|`CMFCPropertyPage::CreateObject`|Wird vom Framework, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|`CMFCPropertyPage::GetThisClass`|Wird vom Framework, um ein Zeiger auf [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)\-Objekt abzurufen, das diesem Klassentyp zugeordnet ist.|  
|`CMFCPropertyPage::OnSetActive`|Diese Memberfunktion wird vom Framework aufgerufen, wenn die Seite vom Benutzer ausgewählt wird und die aktuelle Seite ist.  \(Überschreibungen [CPropertyPage::OnSetActive](../Topic/CPropertyPage::OnSetActive.md).\)|  
|`CMFCPropertyPage::PreTranslateMessage`|Übersetzt Fenstermeldungen, bevor sie an den [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows\-Funktionen weitergeleitet werden.  Weitere Informationen und Methodensyntax finden Sie unter [CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md).  \(Überschreibungen `CPropertyPage::PreTranslateMessage`.\)|  
  
## Hinweise  
 Die Klasse stellt `CMFCPropertyPage` die einzelnen Seiten eines Eigenschaftenblatts dar; andernfalls wird als ein Dialogfeld im Registerformat.  
  
 Verwenden Sie die `CMFCPropertyPage`\-Klasse zusammen mit der [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md)\-Klasse.  Um Menüs auf einer Eigenschaftenseite zu verwenden, ersetzen Sie alle Vorkommen der `CPropertyPage`\-Klasse durch die `CMFCPropertyPage`\-Klasse.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog\-Klasse](../../mfc/reference/cdialog-class.md)  
  
 [CPropertyPage](../../mfc/reference/cpropertypage-class.md)  
  
 [CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md)  
  
## Anforderungen  
 **Header:** afxpropertypage.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCPropertySheet Class](../../mfc/reference/cmfcpropertysheet-class.md)