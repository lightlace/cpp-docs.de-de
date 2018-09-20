---
title: Visualisierungs-Manager | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Visualization Manager
ms.assetid: c9dd1365-27ac-42e5-8caa-1004525b4129
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fce4b036c6a6ae3692353ae02e7d36eb5ddfd1e1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46398484"
---
# <a name="visualization-manager"></a>Visualisierungs-Manager

Visuelle Manager ist ein Objekt, das die Darstellung einer ganzen Anwendung steuert. Er fungiert als eine einzelne Klasse, in dem Sie alle der Zeichencode für Ihre Anwendung einfügen. Die MFC-Bibliothek enthält mehrere Erscheinungsbild-Manager. Sie können auch Ihre eigenen visuellen Manager erstellen, wenn Sie eine benutzerdefinierte Ansicht für Ihre Anwendung erstellen möchten. Die folgenden Abbildungen zeigen die gleiche Anwendung aus, wenn verschiedene Erscheinungsbild-Manager aktiviert sind:

![Von CMFCVisualManagerWindows gerenderte MyApp](../mfc/media/vmwindows.png "Vmwindows") "MyApp", die den visuellen Manager mit CMFCVisualManagerWindows verwendet.

![Von CMFCVisualManagerVS2005 gerenderte MyApp](../mfc/media/vmvs2005.png "vmvs2005") "MyApp", die den visuellen CMFCVisualManagerVS2005-Manager verwendet.

![Von CMFCVisualManagerOfficeXP gerenderte MyApp](../mfc/media/vmofficexp.png "Vmofficexp") "MyApp", die den visuellen CMFCVisualManagerOfficeXP-Manager verwendet.

![Von CMFCVisualManagerOffice2003 gerenderte MyApp](../mfc/media/vmoffice2003.png "vmoffice2003") "MyApp", die den visuellen CMFCVisualManagerOffice2003-Manager verwendet.

![Von CMFCVisualManagerOffice2007 gerenderte MyApp](../mfc/media/msoffice2007.png "msoffice2007") "MyApp", die den visuellen CMFCVisualManagerOffice2007-Manager verwendet.

Standardmäßig behält der visuelle Manager der Zeichencode für mehrere GUI-Elemente. Um benutzerdefinierte Benutzeroberflächenelemente zu gewährleisten, müssen Sie verwandten Zeichenmethoden der visuellen Manager außer Kraft zu setzen. Die Liste der Methoden, finden Sie unter [CMFCVisualManager-Klasse](../mfc/reference/cmfcvisualmanager-class.md). Die Methoden, die Sie überschreiben können, um eine benutzerdefinierte Darstellung bereitstellen, sind alle Methoden, die mit `OnDraw`.

Ihre Anwendung kann haben nur eine `CMFCVisualManager` Objekt. Um einen Zeiger auf den visuellen Manager für Ihre Anwendung zu erhalten, rufen Sie die statische Funktion [CMFCVisualManager::GetInstance](../mfc/reference/cmfcvisualmanager-class.md#getinstance). Da alle Erscheinungsbild-Manager von erben `CMFCVisualManager`, `CMFCVisualManager::GetInstance` Methode wird ein Zeiger auf den entsprechenden visuellen Manager abgerufen, auch wenn Sie einen benutzerdefinierten visuellen Manager erstellen.

Wenn Sie einen benutzerdefinierten visuellen Manager erstellen möchten, müssen Sie es über einen visuellen Manager ableiten, die bereits vorhanden ist. Ist die Standardklasse für die Ableitung `CMFCVisualManager`. Allerdings können Sie einen anderen visuellen Manager, wenn es eine bessere vorstellungen für Ihre Anwendung. Angenommen, Sie verwenden möchten. die `CMFCVisualManagerOffice2007` visuellen Manager sollte jedoch nur zum Ändern des Aussehens von Trennzeichen, leiten Sie können Ihre benutzerdefinierte Klasse von `CMFCVisualManagerOffice2007`. In diesem Szenario sollten Sie nur die Methoden zum Zeichnen von Trennzeichen überschrieben.

Es gibt zwei Möglichkeiten, die einen bestimmten visuellen Manager für Ihre Anwendung zu verwenden. Eine Möglichkeit besteht darin, rufen Sie die [CMFCVisualManager::SetDefaultManager](../mfc/reference/cmfcvisualmanager-class.md#setdefaultmanager) Methode und übergeben Sie die entsprechenden visuellen Manager als Parameter. Im folgenden Codebeispiel wird dargestellt, wie Sie die `CMFCVisualManagerVS2005` visuellen Manager mit dieser Methode:

```cpp
CMFCVisualManager::SetDefaultManager (RUNTIME_CLASS (CMFCVisualManagerVS2005));
```

Eine andere Möglichkeit, einen visuellen Manager in Ihrer Anwendung zu verwenden ist, die sie manuell erstellen. Die Anwendung wird dann dieser neuen visuellen Manager für das gesamte Rendering verwenden. Aber da er nur einmal auftreten darf `CMFCVisualManager` Objekt pro Anwendung, müssen Sie den aktuellen visuellen Manager zu löschen, bevor Sie eine neue Ressourcengruppe erstellen. Im folgenden Beispiel `CMyVisualManager` ist ein benutzerdefinierter visual-Manager, das von abgeleitet ist `CMFCVisualManager`. Die folgende Methode ändert, welche visuellen Manager verwendet wird, um Ihre Anwendung je nach einem Index anzuzeigen:

```cpp
void CMyApp::SetSkin (int index)
{
    if (CMFCVisualManager::GetInstance() != NULL)
    {
        delete CMFCVisualManager::GetInstance();
    }

    switch (index)
    {
    case DEFAULT_STYLE:
        // The following statement creates a new CMFCVisualManager
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

[Elemente der Benutzeroberfläche](../mfc/user-interface-elements-mfc.md)<br/>
[CMFCVisualManager-Klasse](../mfc/reference/cmfcvisualmanager-class.md)
