---
title: "Hosten eines Windows Form-Benutzersteuerelements als MFC-Dialogfeld"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Hosten eines Windows Forms-Steuerelements [C++]"
  - "MFC [C++], Windows Forms-Unterstützung"
  - "Windows Forms [C++], Hosten als MFC-Dialogfeld"
ms.assetid: 0434a9d7-8b14-48e6-ad69-9ba9a684677a
caps.latest.revision: 16
caps.handback.revision: "16"
ms.author: "mblome"
manager: "ghogen"
---
# Hosten eines Windows Form-Benutzersteuerelements als MFC-Dialogfeld
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC stellt die Vorlagenklasse [CWinFormsDialog](../mfc/reference/cwinformsdialog-class.md) zur Verfügung, sodass Sie ein Windows Forms\-Benutzersteuerelement \(<xref:System.Windows.Forms.UserControl>\) in einem MFC\-Dialogfeld mit oder ohne Modus hosten können.  `CWinFormsDialog` wird von der MFC\-Klasse [CDialog](../mfc/reference/cdialog-class.md) abgeleitet, sodass das Dialogfeld mit oder ohne Modus gestartet werden kann.  
  
 Der Prozess, der von `CWinFormsDialog` zum Hosten des Benutzersteuerelements verwendet wird, ähnelt dem Prozess, der unter [Hosten eines Windows Form\-Benutzersteuerelements in einem MFC\-Dialogfeld](../dotnet/hosting-a-windows-form-user-control-in-an-mfc-dialog-box.md) beschrieben ist.  `CWinFormsDialog` verwaltet jedoch die Initialisierung und das Hosten des Benutzersteuerelements, sodass es nicht manuell programmiert werden muss.  
  
 Eine Beispielanwendung, in der Windows Forms angezeigt werden, die mit MFC verwendet werden, finden Sie im Artikel zur [Integration von MFC und Windows Forms](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en).  
  
### So erstellen Sie die MFC\-Hostanwendung  
  
1.  Erstellen Sie ein MFC\-Anwendungsprojekt.  
  
     Klicken Sie im Menü **Datei** auf **Neu** und dann auf **Projekt**.  Wählen Sie im Ordner **Visual C\+\+** die Option **MFC\-Anwendung** aus.  
  
     Geben Sie im Feld **Name** die Zeichenfolge `MFC03` ein, und ändern Sie die Projektmappeneinstellung in **Hinzufügen**.Klicken Sie auf **OK**.  
  
     Übernehmen Sie im **MFC\-Anwendungs\-Assistent** alle Standardeinstellungen, und klicken Sie dann auf **Fertig stellen**.  Dies erstellt eine MFC\-Anwendung mit einem MDI \(Multiple Document Interface\).  
  
2.  Konfigurieren des Projekts.  
  
     Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf den Projektknoten **MFC03**, und wählen Sie **Eigenschaften** aus.  Das Dialogfeld **Eigenschaftenseiten** wird angezeigt.  
  
     Wählen Sie im Dialogfeld **Eigenschaftenseiten** in der Baumstruktur **Konfigurationseigenschaften** die Option **Allgemein** aus, und legen Sie anschließend im Abschnitt **Projektstandards** die **Common Language Runtime\-Unterstützung** auf **Common Language Runtime\-Unterstützung \(\/clr\)** fest.  Klicken Sie auf **OK**.  
  
3.  Fügen Sie dem .NET\-Steuerelement einen Verweis hinzu.  
  
     Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf den Projektknoten **MFC03**, und wählen Sie dann **Hinzufügen** und **Verweise**.  Klicken Sie in der **Eigenschaftenseite** auf **Neuen Verweis hinzufügen**, wählen Sie WindowsControlLibrary1 \(unter der Registerkarte **Projekte**\) aus, und klicken Sie auf **OK**.  Dadurch wird ein Verweis in Form einer [\/FU](../build/reference/fu-name-forced-hash-using-file.md)\-Compileroption hinzugefügt, damit das Programm kompiliert wird; außerdem wird WindowsControlLibrary1.dll in das Projektverzeichnis `MFC03` kopiert, damit das Programm ausgeführt wird.  
  
4.  Fügen Sie in der Datei stdafx.h nach den vorhandenen `#include`\-Anweisungen die Zeichenfolge `#include <afxwinforms.h>` ein.  
  
5.  Fügen Sie eine neue Klasse hinzu, die `CDialog` als Unterklasse verwendet.  
  
     Klicken Sie mit der rechten Maustaste auf den Projektnamen, und fügen Sie eine MFC\-Klasse mit dem Namen CHostForWinForm hinzu, die `CDialog` als Unterklasse verwendet.  Da Sie die Dialogfeldressource nicht benötigen, können Sie die ID der Ressource löschen. \(Wählen Sie die Ressourcenansicht aus, erweitern Sie den Ordner Dialog, und löschen Sie die Ressource IDD\_HOSTFORWINFORM.  Entfernen Sie dann alle Verweise auf die ID aus dem Code.\)  
  
6.  Ersetzen Sie in den Dateien CHostForWinForm.h und CHostForWinForm.cpp `CDialog` durch `CWinFormsDialog<WindowsControlLibrary1::UserControl1>`.  
  
7.  Rufen Sie in der CHostForWinForm\-Klasse DoModal auf.  
  
     Fügen Sie in der Datei MFC03.cpp die Zeichenfolge `#include "HostForWinForm.h"` hinzu.  
  
     Fügen Sie in der Definition von CMFC03App::InitInstance vor der return\-Anweisung Folgendes hinzu:  
  
     `CHostForWinForm m_HostForWinForm;`  
  
     `m_HostForWinForm.DoModal();`  
  
8.  Erstellen Sie das Projekt, und führen Sie es aus.  
  
     Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**.  
  
     Klicken Sie im Menü **Debuggen** auf **Starten ohne Debuggen**.  
  
     Als Nächstes fügen Sie Code zum Überwachen des Zustands eines Steuerelements in den Windows Forms aus der MFC\-Anwendung hinzu.  
  
9. Fügen Sie einen Handler für OnInitDialog hinzu.  
  
     Zeigen Sie das **Eigenschaftenfenster** an \(F4\).  Wählen Sie in **Klassenansicht** CHostForWinForm aus.  Wählen Sie im Fenster **Eigenschaften** Überschreibungen aus, und klicken Sie in der Zeile für OnInitDialog in der linken Spalte auf \< Hinzufügen \>.  Dadurch wird in CHostForWinForm.h die folgende Zeile hinzugefügt:  
  
    ```  
    virtual BOOL OnInitDialog();  
    ```  
  
10. Definieren Sie OnInitDialog \(in CHostForWinForm.cpp\) wie folgt:  
  
    ```  
    BOOL CHostForWinForm::OnInitDialog() {  
       CWinFormsDialog<WindowsControlLibrary1::UserControl1>::OnInitDialog();  
       GetControl()->button1->Click += MAKE_DELEGATE(System::EventHandler, OnButton1);  
       return TRUE;  
    }  
    ```  
  
11. Fügen Sie anschließend den OnButton1\-Handler hinzu.  Fügen Sie dem öffentlichen Abschnitt der CHostForWinForm\-Klasse in CHostForWinForm.h die folgenden Zeilen hinzu:  
  
    ```  
    virtual void OnButton1( System::Object^ sender, System::EventArgs^ e );  
  
    BEGIN_DELEGATE_MAP( CHostForWinForm )  
       EVENT_DELEGATE_ENTRY( OnButton1, System::Object^, System::EventArgs^ );  
    END_DELEGATE_MAP()  
    ```  
  
     Fügen Sie in CHostForWinForm.cpp die folgende Definition hinzu:  
  
    ```  
    void CHostForWinForm::OnButton1( System::Object^ sender, System::EventArgs^ e )   
    {  
       System::Windows::Forms::MessageBox::Show("test");  
    }  
    ```  
  
12. Erstellen Sie das Projekt, und führen Sie es aus.  Wenn Sie auf die Schaltfläche klicken, die sich im Windows Form befindet, wird der Code in der MFC\-Anwendung ausgeführt.  
  
     Als Nächstes fügen Sie Code hinzu, mit dem der Wert aus dem MFC\-Code im Textfeld des Windows Forms angezeigt wird.  
  
13. Fügen Sie in CHostForWinForm.h im öffentlichen Abschnitt der CHostForWinForm\-Klasse die folgende Deklaration hinzu:  
  
    ```  
    CString m_sEditBoxOnWinForm;  
    ```  
  
14. Fügen Sie in der Definition von DoDataExchange in CHostForWinForm.cpp am Ende der Funktion die folgenden drei Zeilen hinzu:  
  
    ```  
    if (pDX->m_bSaveAndValidate)  
       m_sEditBoxOnWinForm = CString( GetControl()->textBox1->Text);  
    else  
       GetControl()->textBox1->Text = gcnew System::String(m_sEditBoxOnWinForm);  
    ```  
  
15. Fügen Sie in der Definition von OnButton1 in CHostForWinForm.cpp am Ende der Funktion die folgenden drei Zeilen hinzu:  
  
    ```  
    this->UpdateData(TRUE);  
    System::String ^ z = gcnew System::String(m_sEditBoxOnWinForm);  
    System::Windows::Forms::MessageBox::Show(z);  
    ```  
  
16. Erstellen Sie das Projekt, und führen Sie es aus.  
  
## Siehe auch  
 <xref:System.Windows.Forms.UserControl?displayProperty=fullName>   
 [Verwenden eines Windows Form\-Benutzersteuerelements in MFC](../dotnet/using-a-windows-form-user-control-in-mfc.md)