---
title: "Erweitern von modalen Dialogfeldern"
ms.custom: na
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "Modale Dialogfelder in Visual Studio-Erweiterungen"
  - "Visual Studio-Erweiterungen, modale Dialogfelder"
ms.assetid: 478743dc-9fd9-46d7-9739-859fb8841a4f
caps.latest.revision: 11
caps.handback.revision: "11"
manager: "douge"
---
# Erweitern von modalen Dialogfeldern
Um funktionale und visuelle Kompatibilität mit Visual Studio zu gewährleisten, sollten Sie modale Dialogfelder für Visual Studio\-Erweiterungen durch Ableiten von Dialogfeldfenstern aus dem <xref:Microsoft.VisualStudio.PlatformUI.DialogWindow?displayProperty=fullName>\-Objekt erstellen. In auf diese Weise abgeleiteten Dialogfeldern können Sie außerdem zusätzliche Funktionen bereitstellen. Beispielsweise können Sie Ziele für die F1\-Hilfe festlegen und das Minimieren und Maximieren des Fensters aktivieren.  
  
## Erstellen von modalen Dialogfeldern  
  
1.  Fügen Sie in Ihrem Projekt einen Verweis auf System.XAML hinzu.  
  
2.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf das Projekt, klicken Sie auf **Hinzufügen** und anschließend auf **Fenster**.  
  
3.  Geben Sie einen Namen für das Fenster ein, und klicken Sie dann auf **Hinzufügen**.  
  
     Ein leeres XAML\-Fenster wird im Designer angezeigt.  
  
4.  Fügen Sie im `Window`\-Element auf oberster Ebene eine Namespace\-Deklaration für <xref:Microsoft.VisualStudio.PlatformUI> hinzu, und ändern Sie das `Window`\-Element in ein <xref:Microsoft.VisualStudio.PlatformUI.DialogWindow?displayProperty=fullName>\-Element, wie im folgenden Beispiel dargestellt.  
  
     [!CODE [VSModalDialog#02](../CodeSnippet/VS_Snippets_VSSDK/vsmodaldialog#02)]  
  
5.  Fügen Sie Schaltflächen, Bezeichnungen und andere Steuerelemente aus der **Toolbox** hinzu, geben Sie die Bezeichnungen ein, und passen Sie die Darstellung des Dialogfelds an.  
  
6.  Wechseln Sie zur Codeansicht.  
  
7.  Legen Sie in der Klassendefinition fest, dass die Klasse von <xref:Microsoft.VisualStudio.PlatformUI.DialogWindow> erbt. \(Die Klasse erbt standardmäßig von <xref:System.Windows.Window?displayProperty=fullName>.\)  
  
8.  Fügen Sie Ereignishandler für Schaltflächen und andere Steuerelemente hinzu.  
  
#### So fügen Sie einem modalen Dialogfeld F1\-Hilfe hinzu  
  
1.  Fügen Sie im Konstruktor einen Parameter hinzu, der eine Zeichenfolge als Argument akzeptiert, und richten Sie mit dem gleichen Parameter den Konstruktor so ein, dass er vom Basiskonstruktor erbt, wie im folgenden Beispiel gezeigt.  
  
     [!CODE [VSModalDialog#12](../CodeSnippet/VS_Snippets_VSSDK/vsmodaldialog#12)]  
  
     Dieser Konstruktor legt die Eigenschaft <xref:Microsoft.VisualStudio.PlatformUI.DialogWindowBase.HasHelpButton*> auf `true` fest und ermöglicht die Verwendung der empfangenen Zeichenfolge als Schlüsselwort, wenn ein Benutzer F1 drückt oder auf die Schaltfläche **Hilfe** klickt.  
  
#### So fügen Sie in einem modalen Dialogfeld Schaltflächen zum Minimieren und Maximieren hinzu  
  
1.  Legen Sie in der Konstruktorfunktion die Eigenschaften <xref:Microsoft.VisualStudio.PlatformUI.DialogWindow.hasMinimizeButton*> und <xref:Microsoft.VisualStudio.PlatformUI.DialogWindow.hasHMaximizeButton*> auf `true` fest, wie im folgenden Beispiel gezeigt.  
  
     [!CODE [VSModalDialog#13](../CodeSnippet/VS_Snippets_VSSDK/vsmodaldialog#13)]  
  
    > [!WARNING]
    >  Wenn die Schaltflächen **Minimieren** und **Maximieren** angezeigt werden, wird die Schaltfläche **Hilfe** ausgeblendet, selbst wenn die Eigenschaft <xref:Microsoft.VisualStudio.PlatformUI.DialogWindowBase.HasHelpButton*> auf `true` festgelegt ist.  
  
## Beispiel  
 Das folgende Beispiel zeigt ein modales Dialogfeld mit zwei Konstruktoren. Der erste Konstruktor akzeptiert ein F1\-Schlüsselwort als Argument und zeigt eine Schaltfläche **Hilfe** an. Der zweite Konstruktor akzeptiert keine Argumente, zeigt jedoch die Schaltflächen **Minimieren** und **Maximieren** an. Wenn Sie auf die Schaltfläche **Ja** klicken, wird eine zweite Instanz des Dialogfelds mit aktivierter Hilfe aufgerufen.  
  
 [!CODE [VSModalDialog#01](../CodeSnippet/VS_Snippets_VSSDK/vsmodaldialog#01)]  
  
 [!CODE [VSModalDialog#11](../CodeSnippet/VS_Snippets_VSSDK/vsmodaldialog#11)]  
  
 Im folgende Code wird das Dialogfeld von einem Ereignishandler aufgerufen.  
  
 [!CODE [VSModalDialog#21](../CodeSnippet/VS_Snippets_VSSDK/vsmodaldialog#21)]  
  
## Siehe auch  
 [Erstellen und Verwalten von modalen Dialogfeldern](../Topic/Creating%20and%20Managing%20Modal%20Dialog%20Boxes.md)