---
title: Hosten ein Windows Form Benutzersteuerelements als MFC-Dialogfeld | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], Windows Forms support
- Windows Forms [C++], hosting as MFC Dialog
- hosting Windows Forms control [C++]
ms.assetid: 0434a9d7-8b14-48e6-ad69-9ba9a684677a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 47914a73880f5cea13f1bc64c231604a0d5d05dd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46073805"
---
# <a name="hosting-a-windows-form-user-control-as-an-mfc-dialog-box"></a>Hosten eines Windows Form-Benutzersteuerelements als MFC-Dialogfeld
MFC stellt die Vorlagenklasse [CWinFormsDialog](../mfc/reference/cwinformsdialog-class.md) , damit Sie ein Windows Forms-Benutzersteuerelement hosten können (<xref:System.Windows.Forms.UserControl>) in einer MFC-Dialogfeld mit oder ohne Modus. `CWinFormsDialog` wird von der MFC-Klasse abgeleitet [CDialog](../mfc/reference/cdialog-class.md), sodass Sie das Dialogfeld mit oder ohne Modus gestartet werden kann.  
  
 Der Prozess, `CWinFormsDialog` zum Hosten des Benutzersteuerelements verwendet wird, wird der ähnlich wie in [hosten ein Windows Form-Benutzersteuerelements in MFC-Dialogfeld](../dotnet/hosting-a-windows-form-user-control-in-an-mfc-dialog-box.md). `CWinFormsDialog` verwaltet jedoch die Initialisierung und das Hosten des Benutzersteuerelements, sodass es nicht manuell programmiert werden muss.  
  
 Eine beispielanwendung, die Windows Forms, die mit MFC verwendet wird, finden Sie unter [MFC und Windows Forms-Integration](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en).  
  
### <a name="to-create-the-mfc-host-application"></a>So erstellen Sie die MFC-Hostanwendung  
  
1.  Erstellen Sie ein MFC-Anwendungsprojekt.  
  
     Auf der **Datei** , wählen Sie im Menü **neu**, und klicken Sie dann auf **Projekt**. In der **Visual C++** Ordner **MFC-Anwendung**.  
  
     In der **Namen** geben `MFC03` , und ändern Sie die projektmappeneinstellung in **zu Projektmappe hinzufügen**. Klicken Sie auf **OK**.  
  
     In der **MFS-Anwendungsassistenten**, übernehmen Sie alle Standardeinstellungen, und klicken Sie dann auf **Fertig stellen**. Dies erstellt eine MFC-Anwendung mit einem MDI (Multiple Document Interface).  
  
2.  Konfigurieren des Projekts.  
  
     In **Projektmappen-Explorer**, mit der rechten Maustaste die **MFC03** Projektknoten, und wählen Sie **Eigenschaften**. Die **Eigenschaftenseiten** Dialogfeld wird angezeigt.  
  
     In der **Eigenschaftenseiten** Dialogfeld der **Konfigurationseigenschaften** Strukturansicht-Steuerelement, auf **allgemeine**, klicken Sie dann in der **Projektstandards**legen **Common Language Runtime-Unterstützung** zu **Common Language Runtime-Unterstützung (/ Clr)**. Klicken Sie auf **OK**.  
  
3.  Fügen Sie dem .NET-Steuerelement einen Verweis hinzu.  
  
     In **Projektmappen-Explorer**, mit der rechten Maustaste die **MFC03** Projektknoten und wählen **hinzufügen**, **Verweise**. In der **Eigenschaftenseite**, klicken Sie auf **neuen Verweis hinzufügen**, wählen Sie WindowsControlLibrary1 (unter der **Projekte** Registerkarte), und klicken Sie auf **OK**. Dies fügt einen Verweis in Form einer [/FU](../build/reference/fu-name-forced-hash-using-file.md) -Compileroption, damit das Programm kompiliert wird; außerdem wird WindowsControlLibrary1.dll in kopiert die `MFC03` Projektverzeichnis, damit das Programm ausgeführt wird.  
  
4.  Fügen Sie in der Datei stdafx.h nach den vorhandenen `#include <afxwinforms.h>`-Anweisungen die Zeichenfolge `#include` ein.  
  
5.  Fügen Sie eine neue Klasse hinzu, die `CDialog` als Unterklasse verwendet.  
  
     Klicken Sie mit der rechten Maustaste auf den Projektnamen, und fügen Sie eine MFC-Klasse mit dem Namen CHostForWinForm hinzu, die `CDialog` als Unterklasse verwendet. Da Sie die Dialogfeldressource nicht benötigen, können Sie die ID der Ressource löschen. (Wählen Sie die Ressourcenansicht aus, erweitern Sie den Ordner Dialog, und löschen Sie die Ressource IDD_HOSTFORWINFORM.  Entfernen Sie dann alle Verweise auf die ID aus dem Code.)  
  
6.  Ersetzen Sie in den Dateien CHostForWinForm.h und CHostForWinForm.cpp `CDialog` durch `CWinFormsDialog<WindowsControlLibrary1::UserControl1>`.  
  
7.  Rufen Sie in der CHostForWinForm-Klasse DoModal auf.  
  
     Fügen Sie in der Datei MFC03.cpp die Zeichenfolge `#include "HostForWinForm.h"` hinzu.  
  
     Fügen Sie in der Definition von CMFC03App::InitInstance vor der return-Anweisung Folgendes hinzu:  
  
    ```cpp
    CHostForWinForm m_HostForWinForm;
    m_HostForWinForm.DoModal();
    ```
  
8.  Erstellen Sie das Projekt, und führen Sie es aus.  
  
     Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**.  
  
     Auf der **Debuggen** Menü klicken Sie auf **Starten ohne debugging**.  
  
     Als Nächstes fügen Sie Code zum Überwachen des Zustands eines Steuerelements in den Windows Forms aus der MFC-Anwendung hinzu.  
  
9. Fügen Sie einen Handler für OnInitDialog hinzu.  
  
     Anzeigen der **Eigenschaften** Fenster (F4). In **Klassenansicht**, wählen Sie CHostForWinForm aus. In der **Eigenschaften** , wählen Sie überschreibt, und klicken Sie in der Zeile für OnInitDialog, in der linken Spalte und wählen \< hinzufügen >. Dadurch wird in CHostForWinForm.h die folgende Zeile hinzugefügt:  
  
    ```cpp  
    virtual BOOL OnInitDialog();  
    ```  
  
10. Definieren Sie OnInitDialog (in CHostForWinForm.cpp) wie folgt:  
  
    ```  
    BOOL CHostForWinForm::OnInitDialog() {  
       CWinFormsDialog<WindowsControlLibrary1::UserControl1>::OnInitDialog();  
       GetControl()->button1->Click += MAKE_DELEGATE(System::EventHandler, OnButton1);  
       return TRUE;  
    }  
    ```  
  
11. Fügen Sie anschließend den OnButton1-Handler hinzu. Fügen Sie dem öffentlichen Abschnitt der CHostForWinForm-Klasse in CHostForWinForm.h die folgenden Zeilen hinzu:  
  
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
  
12. Erstellen Sie das Projekt, und führen Sie es aus. Wenn Sie auf die Schaltfläche klicken, die sich im Windows Form befindet, wird der Code in der MFC-Anwendung ausgeführt.  
  
     Als Nächstes fügen Sie Code hinzu, mit dem der Wert aus dem MFC-Code im Textfeld des Windows Forms angezeigt wird.  
  
13. Fügen Sie in CHostForWinForm.h im öffentlichen Abschnitt der CHostForWinForm-Klasse die folgende Deklaration hinzu:  
  
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
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.UserControl?displayProperty=fullName>   
 [Verwenden eines Windows Form-Benutzersteuerelements in MFC](../dotnet/using-a-windows-form-user-control-in-mfc.md)