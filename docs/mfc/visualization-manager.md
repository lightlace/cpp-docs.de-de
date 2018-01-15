---
title: Visualisierungs-Manager | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: Visualization Manager
ms.assetid: c9dd1365-27ac-42e5-8caa-1004525b4129
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 654ffc0f3fb4c33f153f3389442486ffa86b74a8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="visualization-manager"></a>Visualisierungs-Manager
Der visuelle Manager ist ein Objekt, das die Darstellung einer gesamten Anwendung steuert. Es dient als eine einzelne Klasse, in dem Sie den Zeichencode für Ihre Anwendung einfügen. Die MFC-Bibliothek enthält mehrere visuelle Manager. Sie können auch eigene visual-Manager erstellen, wenn Sie eine benutzerdefinierte Ansicht für Ihre Anwendung erstellen möchten. Folgende Abbildungen zeigen die gleiche Anwendung, wenn unterschiedliche visuelle Manager aktiviert sind:  
  
 ![Mit cmfcvisualmanagerwindows gerenderte MyApp](../mfc/media/vmwindows.png "Vmwindows")  
"MyApp", die den visuellen Manager CMFCVisualManagerWindows verwendet  
  
 ![Mit cmfcvisualmanagervs2005 gerenderte MyApp](../mfc/media/vmvs2005.png "vmvs2005")  
"MyApp", die den visuellen Manager CMFCVisualManagerVS2005 verwendet  
  
 ![Mit cmfcvisualmanagerofficexp gerenderte MyApp](../mfc/media/vmofficexp.png "Vmofficexp")  
"MyApp", die den visuellen Manager CMFCVisualManagerOfficeXP verwendet  
  
 ![Mit cmfcvisualmanageroffice2003 gerenderte MyApp](../mfc/media/vmoffice2003.png "vmoffice2003")  
"MyApp", die den visuellen Manager CMFCVisualManagerOffice2003 verwendet  
  
 ![Mit cmfcvisualmanageroffice2007 gerenderte MyApp](../mfc/media/msoffice2007.png "msoffice2007")  
"MyApp", die den visuellen Manager CMFCVisualManagerOffice2007 verwendet  
  
 Standardmäßig verwaltet visuelle Manager den Zeichencode für mehrere GUI-Elemente. Um Benutzeroberflächenelemente zu gewährleisten, müssen Sie die zugehörigen zeichnen Methoden der visuellen Manager außer Kraft setzen. Die Liste dieser Methoden finden Sie [CMFCVisualManager Klasse](../mfc/reference/cmfcvisualmanager-class.md). Die Methoden, die Sie überschreiben können, um eine benutzerdefinierte Darstellung bereitstellen, sind alle Methoden, die mit beginnt `OnDraw`.  
  
 Die Anwendung kann nur einen haben `CMFCVisualManager` Objekt. Um einen Zeiger auf den visuellen Manager für Ihre Anwendung zu erhalten, rufen Sie die statische Funktion [CMFCVisualManager::GetInstance](../mfc/reference/cmfcvisualmanager-class.md#getinstance). Da alle visuellen Manager erben `CMFCVisualManager`die `CMFCVisualManager::GetInstance` Methode wird einen Zeiger auf dem entsprechenden visual Manager erhalten, auch wenn Sie einen benutzerdefinierten visuellen Manager erstellt.  
  
 Wenn Sie einen benutzerdefinierten visuellen Manager erstellen möchten, müssen Sie es über einen visuellen Manager ableiten, die bereits vorhanden ist. Ist die Standardklasse Ableitung `CMFCVisualManager`. Allerdings können Sie einen anderen visuellen Manager, wenn für Ihre Anwendung soll eine bessere Leistung ähnelt. Beispielsweise mussten Sie zum Verwenden der `CMFCVisualManagerOffice2007` visuellen Manager sollte jedoch nur zum Ändern der Darstellung von Trennzeichen, leiten Sie eine benutzerdefinierte Klasse von `CMFCVisualManagerOffice2007`. In diesem Fall sollten Sie nur die Methoden für das Zeichnen von Trennzeichen überschreiben.  
  
 Es gibt zwei Arten an einen bestimmten visuellen Manager für Ihre Anwendung verwenden. Eine Möglichkeit besteht im Aufrufen der [CMFCVisualManager::SetDefaultManager](../mfc/reference/cmfcvisualmanager-class.md#setdefaultmanager) Methode und übergeben Sie die entsprechenden visuellen Manager als Parameter. Im folgenden Codebeispiel wird dargestellt, wie Sie die `CMFCVisualManagerVS2005` visuellen Manager mit dieser Methode:  
  
```  
CMFCVisualManager::SetDefaultManager (RUNTIME_CLASS (CMFCVisualManagerVS2005));
```  
  
 Die andere Möglichkeit, einen visuellen Manager in Ihrer Anwendung zu verwenden ist, ihn manuell zu erstellen. Die Anwendung wird dann diese neue visuellen Manager für das gesamte Rendering verwenden. Jedoch, da er nur einmal auftreten darf `CMFCVisualManager` Objekt pro Anwendung, müssen Sie die aktuellen visuellen Manager löschen, bevor Sie ein neues Konto erstellen. Im folgenden Beispiel `CMyVisualManager` ist ein benutzerdefinierter visuellen Manager, die abgeleitet ist `CMFCVisualManager`. Die folgende Methode ändert, welche visuellen Manager verwendet wird, um Ihre Anwendung, je nach Index anzuzeigen:  
  
```  
void CMyApp::SetSkin (int index)  
{  
    if (CMFCVisualManager::GetInstance() != NULL)  
 {  
    delete CMFCVisualManager::GetInstance();

 }  
 
    switch (index)  
 {  
    case DEFAULT_STYLE: *// The following statement creates a new CMFCVisualManager  
    CMFCVisualManager::GetInstance();
break;  
 
    case CUSTOM_STYLE:  
    new CMyVisualManager;  
    break; 
 
    default: 
    CMFCVisualManager::GetInstance();
break;  
 }  
 
    CMFCVisualManager::GetInstance()->RedrawAll();

} 
```  
  
## <a name="see-also"></a>Siehe auch  
 [Benutzeroberflächenelemente](../mfc/user-interface-elements-mfc.md)   
 [CMFCVisualManager-Klasse](../mfc/reference/cmfcvisualmanager-class.md)
