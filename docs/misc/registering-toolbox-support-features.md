---
title: "Registrieren von Funktionen zur Toolbox-Unterst&#252;tzung"
ms.custom: na
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "Toolbox [Visual Studio SDK], Registrieren zur Unterstützung"
ms.assetid: 859ed38f-847b-43ba-b363-29af9de98e89
caps.latest.revision: 27
caps.handback.revision: "25"
manager: "douge"
---
# Registrieren von Funktionen zur Toolbox-Unterst&#252;tzung
\<?xml version="1.0" encoding="utf-8"?>
\<caps:SxS xmlns:caps="http://schemas.microsoft.com/build/caps/2013/11">
  \<caps:SxSTarget locale="de-DE">
    \<developerConceptualDocument xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://clixdevr3.blob.core.windows.net/ddueschema/developer.xsd" xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
      <introduction>
        <para>
          \<caps:sentence sentenceid="2723e2c6b6aa00f4785ac5c2c23a9a24" id="tgt1" class="tgtSentence">VSPackages müssen die Registrierung aktualisieren, wenn für die Erweiterung der Standardfunktionen der <ui>Toolbox</ui>:\</caps:sentence>
        </para>
        <list class="bullet">
          <listItem>
            <para>
              \<caps:sentence sentenceid="4f099ff718d1c906c0708854f0e70c26" id="tgt2" class="tgtSentence">in Abhängigkeit vom aktiven Designer oder Editor mithilfe der Funktion zur automatischen Toolbox-Registerkartenauswahl eine bestimmte Toolboxkategorie oder Registerkarte ausgewählt wird.\</caps:sentence>
            </para>
          </listItem>
          <listItem>
            <para>
              \<caps:sentence sentenceid="c8c1cbd26ef8b7fbdc14906e3aa74c2d" id="tgt3" class="tgtSentence">beliebige <codeEntityReference autoUpgrade="true">T:System.Drawing.Design.ToolboxItem</codeEntityReference>-Objekte bereitgestellt werden, die von der <token>vsprvs</token>-Umgebung geladen werden sollen.\</caps:sentence>
            </para>
            <para>
              \<caps:sentence sentenceid="28be4b4dc1f0c65c03bd42c3b6229392" id="tgt4" class="tgtSentence">Diese Elemente werden immer dann von der <token>vsprvs</token>-Umgebung geladen, wenn die <ui>Toolbox</ui> zurückgesetzt wird, entweder durch einen Benutzer über die IDE oder programmgesteuert über die <codeEntityReference autoUpgrade="true">M:Microsoft.VisualStudio.Shell.Interop.IVsPackage.ResetDefaults(System.UInt32)</codeEntityReference>-Methode.\</caps:sentence>
              \<caps:sentence sentenceid="05fbf6bc4325bb960ad140093a4cc0b8" id="tgt5" class="tgtSentence"> Das Zurücksetzen der <ui>Toolbox</ui> generiert ein <codeEntityReference autoUpgrade="true">E:Microsoft.VisualStudio.Shell.Package.ToolboxInitialized</codeEntityReference>-Ereignis im Managed Package Framework.\</caps:sentence>
            </para>
            <alert class="note">
              <para>
                \<caps:sentence sentenceid="763b2987d4c68e27402f2ba6155a4903" id="tgt6" class="tgtSentence">Mit dem Managed Package Framework entwickelte VSPackages verwenden <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.ProvideToolboxItemsAttribute</codeEntityReference>, das auf ihre Implementierung des <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.Package</codeEntityReference>-Objekts angewendet wird, um diese Unterstützung zu registrieren.\</caps:sentence>
              </para>
            </alert>
          </listItem>
          <listItem>
            <para>
              \<caps:sentence sentenceid="ab4e25836bfcc52d7f808f557784d872" id="tgt7" class="tgtSentence">
                <codeEntityReference autoUpgrade="true">T:System.Drawing.Design.ToolboxItem</codeEntityReference>-Objekte mit einem nicht dem Standard entsprechenden Zwischenablageformat durch die Implementierung der <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.Interop.IVsToolboxDataProvider</codeEntityReference>- und <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.Interop.IVsToolboxDataProvider2</codeEntityReference>-Schnittstellen bereitgestellt werden.\</caps:sentence>
            </para>
            <alert class="note">
              <para>
                \<caps:sentence sentenceid="f9ffd216f826e1eb56d39a2f13fecb0e" id="tgt8" class="tgtSentence">Mit dem Managed Package Framework entwickelte VSPackages verwenden eine Instanz des <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.ProvideToolboxFormatAttribute</codeEntityReference>-Objekts, das auf ihre Implementierung der <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.Package</codeEntityReference> angewendet wird, um diese Unterstützung zu registrieren.\</caps:sentence>
              </para>
            </alert>
          </listItem>
          <listItem>
            <para>
              \<caps:sentence sentenceid="8ae24140fff38790768eca31d71d70bb" id="tgt9" class="tgtSentence">dynamische Konfiguration des <codeEntityReference autoUpgrade="true">T:System.Drawing.Design.ToolboxItem</codeEntityReference>-Objekts durch eine Implementierung der <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.IConfigureToolboxItem</codeEntityReference>-Schnittstelle unterstützt werden.\</caps:sentence>
            </para>
            <alert class="note">
              <para>
                \<caps:sentence sentenceid="31ba0c95daf192ac01ab05182af7a150" id="tgt10" class="tgtSentence">Mit dem Managed Package Framework entwickelte VSPackages verwenden <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.ProvideToolboxItemConfigurationAttribute</codeEntityReference>, das auf ihre Implementierung der <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.Package</codeEntityReference> -Klasse angewendet wird, und die <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.ProvideAssemblyFilterAttribute</codeEntityReference>-Klasse, die auf ihre Implementierungen der <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.IConfigureToolboxItem</codeEntityReference>-Klasse angewendet wird, um diese Unterstützung zu registrieren.\</caps:sentence>
              </para>
            </alert>
          </listItem>
        </list>
        <para>
          \<caps:sentence sentenceid="34c67a32bbf56cd6a8ab6faa2ae3972b" id="tgt11" class="tgtSentence">Nicht verwaltete VSPackages müssen die Registrierung explizit aktualisieren, entweder über eine manuell Bearbeitung oder mithilfe einer Registrar-Datei (.rgs).\</caps:sentence>
          \<caps:sentence sentenceid="0c074f973b714863d903764516d41bd1" id="tgt12" class="tgtSentence"> Weitere Informationen finden Sie unter \<link xlink:href="cbd5024b-8061-4a71-be65-7fee90374a35">Creating Registrar Scripts</link>.\</caps:sentence>
        </para>
      </introduction>
      <section>
        <title>
          \<caps:sentence sentenceid="fac22f2c062e119179b2698b87a0976c" id="tgt13" class="tgtSentence">Automatische Toolbox-Registerkartenauswahl\</caps:sentence>
        </title>
        <content>
          <para>
            \<caps:sentence sentenceid="e6d89ba7a2275894bd0a4311572ebcd5" id="tgt14" class="tgtSentence">Editoren oder Designer, die von einer Instanz eines Editorfactory-Objekts bereitgestellt werden, können die Aktivierung bestimmter Toolboxregisterkarten oder -kategorien erfordern, wenn sie selbst ausgeführt werden.\</caps:sentence>
            \<caps:sentence sentenceid="2aea9994cd50698f103cea3139e6546c" id="tgt15" class="tgtSentence"> Wenn z. B. ein Forms-Designer aktiviert ist, soll möglicherweise die Registerkarte <ui>Alle Windows Forms</ui> ausgewählt sein.\</caps:sentence>
          </para>
          <para>
            \<caps:sentence sentenceid="6f78759da35efbb908a3342c27a4d19b" id="tgt16" class="tgtSentence">Damit eine automatische Toolboxkategorieauswahl stattfindet, muss das Factory-Objekt des Designers oder Editors ordnungsgemäß registriert werden.\</caps:sentence>
          </para>
          <para>
            \<caps:sentence sentenceid="9bacb3824409e34e7327639a11d4d456" id="tgt17" class="tgtSentence">Ein geeigneter Registrierungseintrag befindet sich am folgenden Registrierungsspeicherort: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\&lt;Version&gt;\Editor&lt;Editorfactory-GUID&gt;. Dabei steht &lt;Version&gt; für die Versionsnummer des Visual Studio-Releases, z.B. 8.0, und &lt;Editorfactory-GUID&gt; für die GUID der Editorfactory.\</caps:sentence>
          </para>
          <para>
            \<caps:sentence sentenceid="a341d0d50bcaf775526c94112821aa23" id="tgt18" class="tgtSentence">Der Eintrag sollte Folgendes enthalten:\</caps:sentence>
          </para>
          <table>
            <thead>
              <tr>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="b068931cc450442b63f5b3d276ea4297" id="tgt19" class="tgtSentence">Name\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="599dcce2998a6b40b1e38e8c6006cb0a" id="tgt20" class="tgtSentence">Typ\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="37b19816109a32106d109e83bbb3c97d" id="tgt21" class="tgtSentence">Bereich\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="67daf92c833c41c95db874e18fcb2786" id="tgt22" class="tgtSentence">Beschreibung\</caps:sentence>
                  </para>
                </TD>
              </tr>
            </thead>
            <tbody>
              <tr>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="c21f969b5f03d33d43e04f8f136e7682" id="tgt23" class="tgtSentence">Standard\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="2b1bda4361069cdf7a4437824c22893c" id="tgt24" class="tgtSentence">REG_SZ\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="1e0ca5b1252f1f6b1e0ac91be7e7219e" id="tgt25" class="tgtSentence">GUID\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="16c952cba827b0f636670d0a0b4b6619" id="tgt26" class="tgtSentence">Optional.\</caps:sentence>
                    \<caps:sentence sentenceid="660a8e93adc7636c151ae8d05876798d" id="tgt27" class="tgtSentence"> Es kann einen nicht lokalisierten Namen des Editors enthalten.\</caps:sentence>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="2273db0ebdc49bc93d7e68666e04e934" id="tgt28" class="tgtSentence">DefaultToolboxTab\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="2b1bda4361069cdf7a4437824c22893c" id="tgt29" class="tgtSentence">REG_SZ\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="f52e46f5516fde2cbb89abba401e9b7b" id="tgt30" class="tgtSentence"> „Geben Sie hier den Namen Ihrer Registerkarte ein“\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="478d8b9a62f01e9b1e9df04a939f4549" id="tgt31" class="tgtSentence">Der nicht lokalisierte Name der Toolboxregisterkarte, die die Standardregisterkarte der Toolbox darstellt, wenn dieser Editor ausgeführt wird.\</caps:sentence>
                  </para>
                </TD>
              </tr>
            </tbody>
          </table>
          <alert class="note">
            <para>
              \<caps:sentence sentenceid="0273a7826674f69ce9b755e1c0728396" id="tgt32" class="tgtSentence">Es gibt keine <codeEntityReference autoUpgrade="true">T:System.Attribute</codeEntityReference>-Objekte, die diese Registrierungseinträge im Managed Package Framework unterstützen.\</caps:sentence>
            </para>
          </alert>
        </content>
      </section>
      <section>
        <title>
          \<caps:sentence sentenceid="406d7ec5b045e3fa6d28ab7bdad071fc" id="tgt33" class="tgtSentence">Registrieren eines Pakets über die Bereitstellung von Toolboxelementen\</caps:sentence>
        </title>
        <content>
          <alert class="note">
            <para>
              \<caps:sentence sentenceid="ea7536ecc4e646d43cd7678b3a2cd806" id="tgt34" class="tgtSentence">Steuerelemente, die im Visual Studio 10 SDK mit den Steuerelementvorlagen der Toolbox erstellt wurden, werden automatisch registriert.\</caps:sentence>
              \<caps:sentence sentenceid="252fa9bba5d33ff1c7674ed44cec9b1d" id="tgt35" class="tgtSentence"> Weitere Informationen finden Sie unter \<link xlink:href="abbd3c3c-3a6e-4539-bd6c-a5891dead234">How to: Create a Toolbox Control That Uses Windows Forms</link> und \<link xlink:href="9cc34db9-b0d1-4951-a02f-7537fbbb51ad">How to: Create a Toolbox Control That Uses WPF</link>.\</caps:sentence>
            </para>
          </alert>
          <para>
            \<caps:sentence sentenceid="1eb485d0c755c3a22e304e1e3517205c" id="tgt36" class="tgtSentence">Jedes VSPackage, das Objekte des Typs <codeEntityReference autoUpgrade="true">T:System.Drawing.Design.ToolboxItem</codeEntityReference> bereitstellt, muss unter dem eigenen Paketschlüssel (HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\<placeholder>&lt;Version&gt;</placeholder>\Packages\<placeholder>&lt;Package GUID</placeholder>&gt;) über einen Unterschlüssel (<placeholder>Toolbox</placeholder>) verfügen. Dabei steht <placeholder>&lt;Version&gt;</placeholder> für die Versionsnummer des Visual Studio-Releases, z.B. 8.0, und <placeholder>&lt;Paket-GUID&gt;</placeholder> für die GUID des Pakets, das die <ui>Toolbox</ui>-Elemente bereitstellt.\</caps:sentence>
          </para>
          <para>
            \<caps:sentence sentenceid="885003772cee263b20dbf0b67f11e89a" id="tgt37" class="tgtSentence">Dieser Unterschlüssel der Toolbox muss mindestens einen Eintrag enthalten, und zwar einen DWORD-Eintrag namens <placeholder>Default</placeholder><placeholder>Items</placeholder>.\</caps:sentence>
          </para>
          <alert class="note">
            <para>
              \<caps:sentence sentenceid="80d9d920881c34bdd265706b01c7b016" id="tgt38" class="tgtSentence">Der Stammpfad von HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\<placeholder>&lt;Version&gt;</placeholder> kann mit einem alternativen Stamm überschrieben werden, wenn die Visual Studio-Shell initialisiert wird. Alternativ können Sie <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.DefaultRegistryRootAttribute</codeEntityReference> verwenden.\</caps:sentence>
              \<caps:sentence sentenceid="08345caa8a478c2c683614ff7ee5aef6" id="tgt39" class="tgtSentence"> Weitere Informationen finden Sie unter \<link xlink:href="0a22516f-f60e-4476-ac5b-f41e5ffaaf8b">Command-Line Switches (VS SDK)</link>.\</caps:sentence>
            </para>
          </alert>
          <para>
            \<caps:sentence sentenceid="8fd10275b180aafeb02cf6eab3266edd" id="tgt40" class="tgtSentence">Für den Eintrag unter HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\<placeholder>&lt;Version&gt;</placeholder>\Packages\<placeholder>&lt;Paket-GUID</placeholder>&gt;:\</caps:sentence>
          </para>
          <table>
            <thead>
              <tr>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="b068931cc450442b63f5b3d276ea4297" id="tgt41" class="tgtSentence">Name\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="599dcce2998a6b40b1e38e8c6006cb0a" id="tgt42" class="tgtSentence">Typ\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="8d777f385d3dfec8815d20f7496026dc" id="tgt43" class="tgtSentence">Daten\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="67daf92c833c41c95db874e18fcb2786" id="tgt44" class="tgtSentence">Beschreibung\</caps:sentence>
                  </para>
                </TD>
              </tr>
            </thead>
            <tbody>
              <tr>
                <TD>
                  <para>
                    <userInput>Default Items</userInput>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="218feb4305adffe7bdfa1642906f64b3" id="tgt45" class="tgtSentence">REG_DWORD\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="11ba86933abfd864d465dc459b71be06" id="tgt46" class="tgtSentence">Kann ein beliebiger DWORD-Wert sein.\</caps:sentence>
                    \<caps:sentence sentenceid="d7aa2cbe46c93ae4aeebede9e432e4d9" id="tgt47" class="tgtSentence"> Beginnend mit 1.\</caps:sentence>
                    \<caps:sentence sentenceid="c81c30b2d8c1a1a018fa7b3b1328b8df" id="tgt48" class="tgtSentence"> Der Wert wird erhöht, wenn Sie Ihr VSPackage für die Bereitstellung weiterer oder verschiedener Elemente aktualisieren.\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="cb99d539479bcbee846f0af720e40992" id="tgt49" class="tgtSentence">Der Wert von <userInput>Default Items</userInput> muss größer als oder gleich 1 sein, damit <codeEntityReference autoUpgrade="true">T:System.Drawing.Design.ToolboxItem</codeEntityReference>-Objekte zu der <token>vsprvs</token><ui>Toolbox</ui> hinzugefügt werden.\</caps:sentence>
                  </para>
                  <para>
                    \<caps:sentence sentenceid="f0571a767510a284961ca6d63acf9246" id="tgt50" class="tgtSentence">Durch die Änderung des Werts von <userInput>Default Items</userInput> lädt die <token>vsprvs</token>-IDE die aktuelle Instanz eines VSPackage und stellt <codeEntityReference autoUpgrade="true">T:System.Drawing.Design.ToolboxItem</codeEntityReference>-Objekte bereit, anstatt zwischengespeicherte Werte zu verwenden.\</caps:sentence>
                  </para>
                  <para>
                    \<caps:sentence sentenceid="13f2c115731bca807b63798f145edd24" id="tgt51" class="tgtSentence">Im Managed Package Framework wird <userInput>Default Items</userInput> über den Wert festgelegt, der im Konstruktor für die <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.ProvideToolboxItemsAttribute</codeEntityReference>-Instanz verwendet wird, die auf das VSPackage angewendet wird, das <codeEntityReference autoUpgrade="true">T:System.Drawing.Design.ToolboxItem</codeEntityReference>-Objekte bereitstellt.\</caps:sentence>
                  </para>
                </TD>
              </tr>
            </tbody>
          </table>
        </content>
      </section>
      <section>
        <title>
          \<caps:sentence sentenceid="0a3d84a3595199375f2082adfb019664" id="tgt52" class="tgtSentence">Registrieren der Unterstützung für ein nicht dem Standard entsprechenden Format\</caps:sentence>
        </title>
        <content>
          <para>
            \<caps:sentence sentenceid="608ee5aa40176b3a0420156fe444f8db" id="tgt53" class="tgtSentence">Die Registrierung von Zwischenablageformaten, die ein VSPackage eines <codeEntityReference autoUpgrade="true">T:System.Drawing.Design.ToolboxItem</codeEntityReference>-Anbieters unterstützt, ist optional.\</caps:sentence>
          </para>
          <para>
            \<caps:sentence sentenceid="e4663294169b4f37d19e0e3de517dd45" id="tgt54" class="tgtSentence">Wenn das VSPackage eines <codeEntityReference autoUpgrade="true">T:System.Drawing.Design.ToolboxItem</codeEntityReference>-Anbieters keine speziellen Zwischenablageformate erfasst, muss es die <token>vsprvs</token>-Standardformate unterstützen.\</caps:sentence>
            \<caps:sentence sentenceid="d5c1139f1a1016d6ab2a877b15863362" id="tgt55" class="tgtSentence"> Weitere Informationen zu den Standardformaten der Zwischenablage der <ui>Toolbox</ui> finden Sie unter \<link xlink:href="bb84a79e-cd4c-4a58-8871-2513e7119b6e">Toolbox Overview</link>.\</caps:sentence>
          </para>
          <para>
            \<caps:sentence sentenceid="7b78f4bad16f4a9588230a1f06ebd781" id="tgt56" class="tgtSentence">Wenn ein VSPackage Unterstützung für nicht dem Standard entsprechende Formate bereitstellt, müssen diese Formate im Registrierungsschlüssel der <ui>Toolbox</ui> des VSPackages registriert werden (HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\<placeholder>&lt;Version&gt;</placeholder>\Packages\<placeholder>&lt;Paket-GUID</placeholder>&gt;\Toolbox), indem Sie einen Zeichenfolgeneintrag namens <userInput>Formats</userInput> hinzufügen.\</caps:sentence>
          </para>
          <alert class="note">
            <para>
              \<caps:sentence sentenceid="f4b14e0257e75f6499455a6ab037683e" id="tgt57" class="tgtSentence">Ist für VSPackage die Unterstützung benutzerdefinierte Formate registriert, werden nur die benutzerdefinierten Formate unterstützt, die ausdrücklich registriert wurden.\</caps:sentence>
              \<caps:sentence sentenceid="90c4d09b0852a5a47c912742bf428417" id="tgt58" class="tgtSentence"> Ein VSPackage, das benutzerdefinierte Zwischenablageformate registriert, ist nicht länger als die Standardformate der Zwischenablage der <ui>Toolbox</ui> unterstützend registriert, es sei denn, es tut es explizit.\</caps:sentence>
            </para>
          </alert>
          <table>
            <thead>
              <tr>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="b068931cc450442b63f5b3d276ea4297" id="tgt59" class="tgtSentence">Name\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="599dcce2998a6b40b1e38e8c6006cb0a" id="tgt60" class="tgtSentence">Typ\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="8d777f385d3dfec8815d20f7496026dc" id="tgt61" class="tgtSentence">Daten\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="67daf92c833c41c95db874e18fcb2786" id="tgt62" class="tgtSentence">Beschreibung\</caps:sentence>
                  </para>
                </TD>
              </tr>
            </thead>
            <tbody>
              <tr>
                <TD>
                  <para>
                    <userInput>Formats</userInput>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="2b1bda4361069cdf7a4437824c22893c" id="tgt63" class="tgtSentence">REG_SZ\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="8c4c9b084064467c781cbfffd37f0aac" id="tgt64" class="tgtSentence">Verwenden Sie für benutzerdefinierte Formate eine Zeichenfolge für diesen Unterschlüssel.\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="1d77b1ec09cadf78c4dbb508639cdf86" id="tgt65" class="tgtSentence">Gibt ein von einem VSPackage unterstützten benutzerdefinierten Zwischenablageformate an und stellt <ui>Toolbox</ui>-Zwischenablageformate bereits (durch die Implementierung von <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.Interop.IVsToolboxDataProvider</codeEntityReference> und <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.Interop.IVsToolboxDataProvider2</codeEntityReference>).\</caps:sentence>
                  </para>
                  <para>
                    \<caps:sentence sentenceid="aa0b55b3801130d3fa61d18016d3761d" id="tgt66" class="tgtSentence">Die Formate sollten in einer durch Trennzeichen getrennten Liste angegeben werden.\</caps:sentence>
                  </para>
                  <para>
                    \<caps:sentence sentenceid="5314ad0191da454a8786ee2d7948e8bc" id="tgt67" class="tgtSentence">Ein Format kann entweder durch eine Zeichenfolge, das den Namen des Formats enthält, oder den ID-Namen angegeben werden.\</caps:sentence>
                    \<caps:sentence sentenceid="5b50a7a04cf772f538f6f26a0f6a2e7f" id="tgt68" class="tgtSentence"> Ein <codeInline>Formats</codeInline>-Eintrag könnte zum Beispiel <codeInline>'1,13,16,HTML Format'</codeInline> lauten.\</caps:sentence>
                  </para>
                  <para>
                    \<caps:sentence sentenceid="7b723e165aadd5afec36f275a790e35e" id="tgt69" class="tgtSentence">Weitere Informationen über die Zwischenablageformate finden Sie unter <codeEntityReference autoUpgrade="true">T:System.Windows.Forms.DataFormats.Format</codeEntityReference>.\</caps:sentence>
                  </para>
                  <para>
                    \<caps:sentence sentenceid="5e1138c1061d9f0da3ba2248cf906f20" id="tgt70" class="tgtSentence">Im Managed Package Framework stammt der Wert von <userInput>Formats</userInput> aus einer Zeichenfolge, die als Argument für den Konstruktor der Instanz des Objekts <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.ProvideToolboxFormatAttribute</codeEntityReference> verwendet wird, das auf das VSPackage angewendet wird, das Objekte des Typs <codeEntityReference autoUpgrade="true">T:System.Drawing.Design.ToolboxItem</codeEntityReference> bereitstellt.\</caps:sentence>
                  </para>
                </TD>
              </tr>
            </tbody>
          </table>
        </content>
      </section>
      <section>
        <title>
          \<caps:sentence sentenceid="a6d19fb8f05c216ff5fe55ca14a2a4ea" id="tgt71" class="tgtSentence">Registrieren der Unterstützung für die dynamische Konfiguration von Toolboxelementen\</caps:sentence>
        </title>
        <content>
          <para>
            \<caps:sentence sentenceid="f538a1b3970989e37d92248afc1e7175" id="tgt72" class="tgtSentence">Wenn ein VSPackage eine Implementierung von <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.IConfigureToolboxItem</codeEntityReference> bereitstellt, müssen Registrierungseinträge unter HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\<placeholder>&lt;Version&gt;</placeholder>\CLSID \</caps:sentence>
            \<caps:sentence sentenceid="959bee4a50d848fd73b1166208aca146" id="tgt73" class="tgtSentence"> und HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\<placeholder>&lt;Version&gt;</placeholder>\ToolboxItemConfiguration hinzugefügt werden.\</caps:sentence>
          </para>
          <para>
            \<caps:sentence sentenceid="eddc850b2f6fc151bc46ab77e30725c7" id="tgt74" class="tgtSentence">Die Registrierungsdaten unter HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\<placeholder>&lt;Version&gt;</placeholder>\CLSID enthalten die Informationen, die die <token>vsprvs</token>-Umgebung benötigt, um die Implementierung von <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.IConfigureToolboxItem</codeEntityReference> aufzurufen.\</caps:sentence>
          </para>
          <para>
            \<caps:sentence sentenceid="1386157c82000350a78134cd48d0a01f" id="tgt75" class="tgtSentence">Die Daten unter HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\<placeholder>&lt;Version&gt;</placeholder>\ToolboxItemConfiguration werden verwendet, um diejenigen <codeEntityReference autoUpgrade="true">T:System.Drawing.Design.ToolboxItem</codeEntityReference>-Objekte auszuwählen bzw. herauszufiltern, die die Implementierung von <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.IConfigureToolboxItem</codeEntityReference> basierend auf den Assemblies konfiguriert, in denen diese Objekte enthalten sind.\</caps:sentence>
          </para>
          <para>
            \<caps:sentence sentenceid="0392926fcfc94a4c83f1f770772bada6" id="tgt76" class="tgtSentence">Inhalt des Registrierungseintrags HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\<placeholder>&lt;Version&gt;</placeholder>\CLSID:\</caps:sentence>
          </para>
          <alert class="note">
            <para>
              \<caps:sentence sentenceid="ec769d7be1d41706078252624ef75958" id="tgt77" class="tgtSentence">Unter dem Managed Package Framework werden diese Registrierungseinträge durch die <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.ProvideToolboxItemConfigurationAttribute</codeEntityReference>-Instanz erstellt.\</caps:sentence>
              \<caps:sentence sentenceid="61e662916c84c1b431fffc055091ae2f" id="tgt78" class="tgtSentence"> Diese Instanz gehört zu dem VSPackage, das die Konfiguration von <codeEntityReference autoUpgrade="true">T:System.Drawing.Design.ToolboxItem</codeEntityReference> mithilfe von Reflektion bereitstellt.\</caps:sentence>
              \<caps:sentence sentenceid="de93eb2cae64cdbb6f4d167ec41d614d" id="tgt79" class="tgtSentence"> Die Reflektion wird auf dem <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.IConfigureToolboxItem</codeEntityReference>-Element ausgeführt, das dem <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.ProvideToolboxItemConfigurationAttribute</codeEntityReference>-Konstruktor zur Verfügung gestellt wird.\</caps:sentence>
            </para>
          </alert>
          <table>
            <thead>
              <tr>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="b068931cc450442b63f5b3d276ea4297" id="tgt80" class="tgtSentence">Name\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="599dcce2998a6b40b1e38e8c6006cb0a" id="tgt81" class="tgtSentence">Typ\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="8d777f385d3dfec8815d20f7496026dc" id="tgt82" class="tgtSentence">Daten\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="67daf92c833c41c95db874e18fcb2786" id="tgt83" class="tgtSentence">Beschreibung\</caps:sentence>
                  </para>
                </TD>
              </tr>
            </thead>
            <tbody>
              <tr>
                <TD>
                  <para>
                    <placeholder>
                      \<caps:sentence sentenceid="6f8d1b93e4aad53511c85e29ed36b3d0" id="tgt84" class="tgtSentence">(Standard)\</caps:sentence>
                    </placeholder>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="2b1bda4361069cdf7a4437824c22893c" id="tgt85" class="tgtSentence">REG_SZ\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="f53d1cd25e03173ba9eaa4e493636769" id="tgt86" class="tgtSentence">(Optional)\</caps:sentence>
                  </para>
                  <para>
                    \<caps:sentence sentenceid="6a87eeb87aba2f471f9933538ba5181f" id="tgt87" class="tgtSentence">der vollständige Name der Klasse, die <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.IConfigureToolboxItem</codeEntityReference> implementiert\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="1c37c535d0eb265c72aa5a76576f2bb4" id="tgt88" class="tgtSentence">Dieser Wert sollte identisch zu dem Wert sein, der von der <codeEntityReference autoUpgrade="true">P:System.Type.FullName</codeEntityReference>-Eigenschaft der Klasse <codeEntityReference autoUpgrade="true">T:System.Type</codeEntityReference> bereitgestellt wird, die <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.IConfigureToolboxItem</codeEntityReference> implementiert.\</caps:sentence>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <userInput>Assembly</userInput>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="2b1bda4361069cdf7a4437824c22893c" id="tgt89" class="tgtSentence">REG_SZ\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="05cf83fd07d92b5ab7ce201d5b87ff2b" id="tgt90" class="tgtSentence">der vollständige Name der Assembly, die <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.IConfigureToolboxItem</codeEntityReference> bereitstellt\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="c4772e3f307c39b2960cdd923b7366b4" id="tgt91" class="tgtSentence">Dieser Wert muss die vollständige Assemblykennung enthalten, die je nach Assembly Folgendes enthält:\</caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        \<caps:sentence sentenceid="12fb55a0159cd343fe97b6e1cc17ae3b" id="tgt92" class="tgtSentence">einen einfachen Namen\</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        \<caps:sentence sentenceid="229daf89d9d97f2a1853dc435c098350" id="tgt93" class="tgtSentence">eine Versionsnummer\</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        \<caps:sentence sentenceid="12f59160267363adcac910af78ba9fe9" id="tgt94" class="tgtSentence">ein kryptografisches Schlüsselpaar\</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        \<caps:sentence sentenceid="3b44b73b1cb2cbc4060b9cbcc7a15ee4" id="tgt95" class="tgtSentence">eine unterstützte Kultur \</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        \<caps:sentence sentenceid="035cc3c91f117c824750c9b75c34d451" id="tgt96" class="tgtSentence">ein benutzerdefiniertes Feld\</caps:sentence>
                      </para>
                    </listItem>
                  </list>
                  <para>
                    \<caps:sentence sentenceid="b469ad1fd9633b9237f30a61c4195e61" id="tgt97" class="tgtSentence">Der Wert muss eine durch Trennzeichen getrennte Liste der Eigenschaftswerte sein, wie von der <codeEntityReference autoUpgrade="true">P:System.Type.FullName</codeEntityReference>-Eigenschaft der Klasse <codeEntityReference autoUpgrade="true">T:System.Type</codeEntityReference> bereitgestellt, die <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.IConfigureToolboxItem</codeEntityReference> implementiert.\</caps:sentence>
                  </para>
                  <para>
                    \<caps:sentence sentenceid="868d7fd9c23944a7dc3befdb855157a3" id="tgt98" class="tgtSentence">Zum Beispiel:\</caps:sentence>
                  </para>
                  <code>MyPackage.Toolbox, Version=8.0.1200.0, Culture=neutral,PublicKeyToken=abcdef12345ab, Custom=null</code>
                  <para>
                    \<caps:sentence sentenceid="db7d7f783cdc876730a19eaab80d3e1d" id="tgt99" class="tgtSentence">Platzhalterzeichen werden nicht unterstützt.\</caps:sentence>
                  </para>
                  <para>
                    \<caps:sentence sentenceid="852d167aa3eda84033fb45f41fc76a79" id="tgt100" class="tgtSentence">Weitere Informationen über das Format der vollständigen Assemblynamen finden Sie unter <codeEntityReference autoUpgrade="true">P:System.Type.AssemblyQualifiedName</codeEntityReference>.\</caps:sentence>
                  </para>
                  <para>
                    \<caps:sentence sentenceid="06b4cfe85de602da117e4f9806b1dc25" id="tgt101" class="tgtSentence">
                      <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.IConfigureToolboxItem</codeEntityReference>.\</caps:sentence>
                  </para>
                  <para>
                    \<caps:sentence sentenceid="b8fc5d57e7f5c9da0e6f620173b59b83" id="tgt102" class="tgtSentence">Weitere Informationen über Assemblykennung finden Sie unter <codeEntityReference autoUpgrade="true">T:System.Reflection.AssemblyName</codeEntityReference>.\</caps:sentence>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <userInput>Class</userInput>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="2b1bda4361069cdf7a4437824c22893c" id="tgt103" class="tgtSentence">REG_SZ\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="fa22ae8137f4ade1186534bce94a634e" id="tgt104" class="tgtSentence">der vollständige Name der Klasse, die die <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.IConfigureToolboxItem</codeEntityReference>-Schnittstelle implementiert, die von <codeEntityReference autoUpgrade="true">P:System.Type.FullName</codeEntityReference> bereitgestellt wird\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="587bdced1562b4293f8925c25cb38414" id="tgt105" class="tgtSentence">Dieser Wert sollte identisch zu dem Wert sein, der von der <codeEntityReference autoUpgrade="true">P:System.Type.FullName</codeEntityReference>-Eigenschaft der Klasse „Type“ bereitgestellt wird, die <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.IConfigureToolboxItem</codeEntityReference> implementiert.\</caps:sentence>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <userInput>CodeBase</userInput>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="2b1bda4361069cdf7a4437824c22893c" id="tgt106" class="tgtSentence">REG_SZ\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="e70aa13772da060498c0a9438cbed647" id="tgt107" class="tgtSentence">Speicherort der Assembly, der die Implementierung von <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.IConfigureToolboxItem</codeEntityReference> bereitstellt\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="82438db67603b3ff88734e127bf535a9" id="tgt108" class="tgtSentence">Dieser Wert muss der vollqualifizierte Pfad zur Assemblydatei mit der Implementierung von <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.IConfigureToolboxItem</codeEntityReference> sein.\</caps:sentence>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <userInput>InprocServer32</userInput>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="2b1bda4361069cdf7a4437824c22893c" id="tgt109" class="tgtSentence">REG_SZ\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="b1916f95efedfc2c1e075c69ef1a0419" id="tgt110" class="tgtSentence">muss immer auf <codeInline>"C:\WINDOWS\System32\mscoree.dll"</codeInline> festgelegt werden\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="0dae36df49124ebce7a43edffbefd81d" id="tgt111" class="tgtSentence">der prozessinterne Server\</caps:sentence>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <userInput>ThreadingModel</userInput>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="2b1bda4361069cdf7a4437824c22893c" id="tgt112" class="tgtSentence">REG_SZ\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="53a88b1936ddc6ec384670e012774d39" id="tgt113" class="tgtSentence">muss immer auf <codeInline>"Both"</codeInline> festgelegt werden\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="da3fb00d8c8ddf855d94d344868df5f8" id="tgt114" class="tgtSentence">Threadmodell\</caps:sentence>
                  </para>
                </TD>
              </tr>
            </tbody>
          </table>
          <para>
            \<caps:sentence sentenceid="e88c6cc55e7e1ea9edfc2ee69386e0ce" id="tgt115" class="tgtSentence">Inhalt des Registrierungseintrags HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\<placeholder>&lt;Version&gt;</placeholder>\ToolboxItemConfiguration:\</caps:sentence>
          </para>
          <alert class="note">
            <para>
              \<caps:sentence sentenceid="a5b30a50495f0d80d7bbe87e76f93993" id="tgt116" class="tgtSentence">Unter dem Managed Package Framework werden diese Registrierungseinträge durch die <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.ProvideAssemblyFilterAttribute</codeEntityReference>-Instanz erstellt, die an <codeEntityReference autoUpgrade="true">T:System.Type</codeEntityReference> angehängt ist und eine Implementierung von <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.IConfigureToolboxItem</codeEntityReference> bereitstellt.\</caps:sentence>
            </para>
          </alert>
          <table>
            <thead>
              <tr>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="b068931cc450442b63f5b3d276ea4297" id="tgt117" class="tgtSentence">Name\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="599dcce2998a6b40b1e38e8c6006cb0a" id="tgt118" class="tgtSentence">Typ\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="8d777f385d3dfec8815d20f7496026dc" id="tgt119" class="tgtSentence">Daten\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="67daf92c833c41c95db874e18fcb2786" id="tgt120" class="tgtSentence">Beschreibung\</caps:sentence>
                  </para>
                </TD>
              </tr>
            </thead>
            <tbody>
              <tr>
                <TD>
                  <para>
                    <placeholder>
                      \<caps:sentence sentenceid="b1b482331c43e059b6642851f98611ce" id="tgt121" class="tgtSentence">&lt;AssemblyName&gt;\</caps:sentence>
                    </placeholder>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="2b1bda4361069cdf7a4437824c22893c" id="tgt122" class="tgtSentence">REG_SZ\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="06613e92693c4e7f87de647ea60e2cc2" id="tgt123" class="tgtSentence">Spezifikation der Assemblys, die ausgewählt oder gefiltert werden sollen\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="7b6478514dc72c9251c28fcdad27c1c5" id="tgt124" class="tgtSentence">Der Schlüsselname (<placeholder>&lt;AssemblyName&gt;</placeholder>) muss im Format des vollständigen Assemblykennung angegeben werden, das in Abhängigkeit der Assemblys Folgendes enthält:\</caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        \<caps:sentence sentenceid="12fb55a0159cd343fe97b6e1cc17ae3b" id="tgt125" class="tgtSentence">einen einfachen Namen\</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        \<caps:sentence sentenceid="229daf89d9d97f2a1853dc435c098350" id="tgt126" class="tgtSentence">eine Versionsnummer\</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        \<caps:sentence sentenceid="12f59160267363adcac910af78ba9fe9" id="tgt127" class="tgtSentence">ein kryptografisches Schlüsselpaar\</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        \<caps:sentence sentenceid="3b44b73b1cb2cbc4060b9cbcc7a15ee4" id="tgt128" class="tgtSentence">eine unterstützte Kultur \</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        \<caps:sentence sentenceid="035cc3c91f117c824750c9b75c34d451" id="tgt129" class="tgtSentence">ein benutzerdefiniertes Feld\</caps:sentence>
                      </para>
                    </listItem>
                  </list>
                  <para>
                    \<caps:sentence sentenceid="dfad07554fcbe16cc6f49197ad1b3e45" id="tgt130" class="tgtSentence">Der Schlüsselname muss eine durch Trennzeichen getrennte Liste von Eigenschaft-Wert-Paaren sein.\</caps:sentence>
                    \<caps:sentence sentenceid="c432bc44d657c193d5e4024e49a04115" id="tgt131" class="tgtSentence"> Weitere Informationen über das Format der vollständigen Assemblynamen finden Sie im Artikel zur <codeEntityReference qualifyHint="true" autoUpgrade="true">P:System.Type.FullName</codeEntityReference>-Eigenschaft.\</caps:sentence>
                  </para>
                  <para>
                    \<caps:sentence sentenceid="2b947e94bbc763bed850039c3fa4b2ba" id="tgt132" class="tgtSentence">In diesem Wert wird ein Platzhalterzeichen von <codeInline>"*"</codeInline> unterstützt, und jedes nicht angegebene Feld wird wie ein Platzhalter behandelt.\</caps:sentence>
                  </para>
                  <para>
                    \<caps:sentence sentenceid="ecd73916a68f9063aa4abeca273503b5" id="tgt133" class="tgtSentence">Ein Schlüssel mit der Bezeichnung \</caps:sentence>
                  </para>
                  <code>System.Windows.*, Version=8.0.*, Culture=*,PublicKeyToken=*</code>
                  <para>
                    \<caps:sentence sentenceid="b1607f34f4c713f8b6a9ceff6f7b9f01" id="tgt134" class="tgtSentence">wählt z.B. alle Assemblys mit Namespaces unter <codeInline>System.Windows</codeInline> (jedoch nicht <codeInline>System.Windows</codeInline> selbst) für alle Nebenversionen der 8.0-Releases und für alle Kulturen, kryptografischen Schlüsselwerte und benutzerdefinierten Zeichenfolgen aus.\</caps:sentence>
                  </para>
                  <para>
                    \<caps:sentence sentenceid="a92c91c27116d7de58936a1fff3f6163" id="tgt135" class="tgtSentence">Im Managed Package Framework wird der Schlüsselname von <placeholder>&lt;Assemblyname&gt;</placeholder> durch die Zeichenfolge bestimmt, die als Argument an den Konstruktor für die <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.ProvideAssemblyFilterAttribute</codeEntityReference>-Instanz verwendet und auf die Klasse angewendet wurde, die die <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.IConfigureToolboxItem</codeEntityReference>-Schnittstelle implementiert.\</caps:sentence>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <placeholder>
                      \<caps:sentence sentenceid="30b7ce5db4acd676d57f0a7515f6e929" id="tgt136" class="tgtSentence">&lt;ImplementationObject&gt;\</caps:sentence>
                    </placeholder>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="2b1bda4361069cdf7a4437824c22893c" id="tgt137" class="tgtSentence">REG_SZ\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="0ef438b8897679e7a06b476e79ce8b10" id="tgt138" class="tgtSentence">GUID \</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence sentenceid="6863b63f529f42b1a4d4407fc0f915c9" id="tgt139" class="tgtSentence">Der Name des Unterschlüssels von <placeholder>AssemblyName</placeholder> ist der vollqualifizierte Name des <codeEntityReference autoUpgrade="true">T:System.Type</codeEntityReference>s, der die <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.IConfigureToolboxItem</codeEntityReference>-Schnittstelle implementiert.\</caps:sentence>
                  </para>
                  <para>
                    \<caps:sentence sentenceid="344a3b2a62c31a95fbbe405868cbdda9" id="tgt140" class="tgtSentence">Der Wert dieses Unterschlüssel ist die GUID dieses <codeEntityReference autoUpgrade="true">T:System.Type</codeEntityReference>s.\</caps:sentence>
                  </para>
                  <para>
                    \<caps:sentence sentenceid="f153c8b46981efec7618fd13782c2564" id="tgt141" class="tgtSentence">Diese Informationen werden im Managed Package Framework über Reflektion von der Klasse abgerufen, die die <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.IConfigureToolboxItem</codeEntityReference>-Schnittstelle mit einem darauf angewendeten <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.ProvideAssemblyFilterAttribute</codeEntityReference>-Objekt implementiert.\</caps:sentence>
                  </para>
                </TD>
              </tr>
            </tbody>
          </table>
          <para>
            \<caps:sentence sentenceid="07b7affe5f51c729ed0276d01c916588" id="tgt142" class="tgtSentence">Ein Beispiel eines Eintrages unter HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\<placeholder>&lt;Version&gt;</placeholder>\ToolboxItemConfiguration könnte wie folgt lauten:\</caps:sentence>
          </para>
          <para>
            <codeInline>        Vsip.*, Version=2.0.3500</codeInline>
          </para>
          <para>
            <codeInline>            Vsip.ToolboxConfiguration = {YYYYYYYY-YYYY-YYYY-YYYY-YYYYYYYYYYYY}</codeInline>
          </para>
        </content>
      </section>
      <relatedTopics>
        \<link xlink:href="3b052047-f6db-46dd-b3bf-da1c348ee410">Managing the Toolbox</link>
        \<link xlink:href="c3e8b404-7086-4e08-9d07-ab9c509963ca">How To: Provide Custom Toolbox Items Using Interop Assemblies</link>
        <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.ProvideToolboxItemsAttribute</codeEntityReference>
        <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.ProvideToolboxFormatAttribute</codeEntityReference>
        <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.ProvideAssemblyFilterAttribute</codeEntityReference>
        <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.IConfigureToolboxItem</codeEntityReference>
        <codeEntityReference autoUpgrade="true">T:System.Drawing.Design.ToolboxItem</codeEntityReference>
      </relatedTopics>
    </developerConceptualDocument>
  \</caps:SxSTarget>
  \<caps:SxSSource locale="en-US">
    \<developerConceptualDocument xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://clixdevr3.blob.core.windows.net/ddueschema/developer.xsd" xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
      <introduction>
        <para>
          \<caps:sentence id="src1" class="srcSentence">VSPackages must update the registry if they extend the default set of <ui>Toolbox</ui> functionality in any of the following ways:\</caps:sentence>
        </para>
        <list class="bullet">
          <listItem>
            <para>
              \<caps:sentence id="src2" class="srcSentence">Using automatic toolbox tab selection of a particular toolbox category or tab when a particular designer or editor is active.\</caps:sentence>
            </para>
          </listItem>
          <listItem>
            <para>
              \<caps:sentence id="src3" class="srcSentence">Providing any <codeEntityReference autoUpgrade="true">T:System.Drawing.Design.ToolboxItem</codeEntityReference> objects to be loaded by the <token>vsprvs</token> environment.\</caps:sentence>
            </para>
            <para>
              \<caps:sentence id="src4" class="srcSentence">These items are loaded by the <token>vsprvs</token> environment whenever the <ui>Toolbox</ui> is reset, either by a user through the IDE, or programmatically through the <codeEntityReference autoUpgrade="true">M:Microsoft.VisualStudio.Shell.Interop.IVsPackage.ResetDefaults(System.UInt32)</codeEntityReference> method.\</caps:sentence>
              \<caps:sentence id="src5" class="srcSentence"> Resetting of the <ui>Toolbox</ui> generates a <codeEntityReference autoUpgrade="true">E:Microsoft.VisualStudio.Shell.Package.ToolboxInitialized</codeEntityReference> event under the Managed Package Framework.\</caps:sentence>
            </para>
            <alert class="note">
              <para>
                \<caps:sentence id="src6" class="srcSentence">VSPackages developed under the Managed Package Framework use <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.ProvideToolboxItemsAttribute</codeEntityReference> applied to their implementation of the <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.Package</codeEntityReference> object to register this support.\</caps:sentence>
              </para>
            </alert>
          </listItem>
          <listItem>
            <para>
              \<caps:sentence id="src7" class="srcSentence">Providing non-standard Clipboard format <codeEntityReference autoUpgrade="true">T:System.Drawing.Design.ToolboxItem</codeEntityReference> objects by implementing the <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.Interop.IVsToolboxDataProvider</codeEntityReference> and <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.Interop.IVsToolboxDataProvider2</codeEntityReference> interfaces.\</caps:sentence>
            </para>
            <alert class="note">
              <para>
                \<caps:sentence id="src8" class="srcSentence">VSPackages developed under the Managed Package Framework use an instance of the <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.ProvideToolboxFormatAttribute</codeEntityReference> object applied to their implementation of <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.Package</codeEntityReference> to register this support.\</caps:sentence>
              </para>
            </alert>
          </listItem>
          <listItem>
            <para>
              \<caps:sentence id="src9" class="srcSentence">Supporting dynamic configuration of <codeEntityReference autoUpgrade="true">T:System.Drawing.Design.ToolboxItem</codeEntityReference> object through an implementation of the <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.IConfigureToolboxItem</codeEntityReference> interface.\</caps:sentence>
            </para>
            <alert class="note">
              <para>
                \<caps:sentence id="src10" class="srcSentence">VSPackages developed with the Managed Package Framework use <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.ProvideToolboxItemConfigurationAttribute</codeEntityReference> applied to their implementation of the <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.Package</codeEntityReference> class, and the <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.ProvideAssemblyFilterAttribute</codeEntityReference> class applied to their implementations of the <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.IConfigureToolboxItem</codeEntityReference> class to register this support.\</caps:sentence>
              </para>
            </alert>
          </listItem>
        </list>
        <para>
          \<caps:sentence id="src11" class="srcSentence">Unmanaged VSPackages must explicitly update the registry either by manually editing it or by using a Registrar (.rgs) file.\</caps:sentence>
          \<caps:sentence id="src12" class="srcSentence"> For more information, see \<link xlink:href="cbd5024b-8061-4a71-be65-7fee90374a35">Creating Registrar Scripts</link>.\</caps:sentence>
        </para>
      </introduction>
      <section>
        <title>
          \<caps:sentence id="src13" class="srcSentence">Automatic Toolbox Tab Selection\</caps:sentence>
        </title>
        <content>
          <para>
            \<caps:sentence id="src14" class="srcSentence">Editors or designers, provided by an instance of an editor factory object, can require a particular toolbox tab or category to be made active when they are themselves active.\</caps:sentence>
            \<caps:sentence id="src15" class="srcSentence"> For example, if a forms designer is activated, you may want the <ui>All Windows Forms</ui> tab selected.\</caps:sentence>
          </para>
          <para>
            \<caps:sentence id="src16" class="srcSentence">For automatic toolbox category selection to take place, the designer's or editor's factory object must be properly registered.\</caps:sentence>
          </para>
          <para>
            \<caps:sentence id="src17" class="srcSentence">An appropriate registry entry is found in the following registry location: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\&lt;Version&gt;\Editor&lt;Editor Factory GUID&gt;, where &lt;Version&gt; is the version number of the release of Visual Studio, such as 8.0, and &lt;Editor Factory GUID&gt; is the GUID for the editor factory.\</caps:sentence>
          </para>
          <para>
            \<caps:sentence id="src18" class="srcSentence">The entry should contain:\</caps:sentence>
          </para>
          <table>
            <thead>
              <tr>
                <TD>
                  <para>
                    \<caps:sentence id="src19" class="srcSentence">Name\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence id="src20" class="srcSentence">Type\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence id="src21" class="srcSentence">Range\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence id="src22" class="srcSentence">Description\</caps:sentence>
                  </para>
                </TD>
              </tr>
            </thead>
            <tbody>
              <tr>
                <TD>
                  <para>
                    \<caps:sentence id="src23" class="srcSentence">Default\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence id="src24" class="srcSentence">REG_SZ\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence id="src25" class="srcSentence">GUID\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence id="src26" class="srcSentence">Optional.\</caps:sentence>
                    \<caps:sentence id="src27" class="srcSentence"> It can be used to contain a non-localized name of the editor.\</caps:sentence>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    \<caps:sentence id="src28" class="srcSentence">DefaultToolboxTab\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence id="src29" class="srcSentence">REG_SZ\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence id="src30" class="srcSentence"> "Your tab name here"\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence id="src31" class="srcSentence">The non-localized name of the toolbox tab, which is made the default toolbox tab when this editor is active.\</caps:sentence>
                  </para>
                </TD>
              </tr>
            </tbody>
          </table>
          <alert class="note">
            <para>
              \<caps:sentence id="src32" class="srcSentence">There are no <codeEntityReference autoUpgrade="true">T:System.Attribute</codeEntityReference> objects which support these registry entries in the Managed Package Framework.\</caps:sentence>
            </para>
          </alert>
        </content>
      </section>
      <section>
        <title>
          \<caps:sentence id="src33" class="srcSentence">Registering a Package as Providing Toolbox Items\</caps:sentence>
        </title>
        <content>
          <alert class="note">
            <para>
              \<caps:sentence id="src34" class="srcSentence">Controls created with the Toolbox Control templates in the Visual Studio 10 SDK register automatically.\</caps:sentence>
              \<caps:sentence id="src35" class="srcSentence"> For more information, see \<link xlink:href="abbd3c3c-3a6e-4539-bd6c-a5891dead234">How to: Create a Toolbox Control That Uses Windows Forms</link> and \<link xlink:href="9cc34db9-b0d1-4951-a02f-7537fbbb51ad">How to: Create a Toolbox Control That Uses WPF</link>.\</caps:sentence>
            </para>
          </alert>
          <para>
            \<caps:sentence id="src36" class="srcSentence">Any VSPackage providing <codeEntityReference autoUpgrade="true">T:System.Drawing.Design.ToolboxItem</codeEntityReference> objects must have a subkey, <placeholder>Toolbox</placeholder>, under its own package key, HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\<placeholder>&lt;Version&gt;</placeholder>\Packages\<placeholder>&lt;Package GUID</placeholder>&gt;, where <placeholder>&lt;Version&gt;</placeholder> is the version number of the release of Visual Studio, such as 8.0, and <placeholder>&lt;Package GUID&gt;</placeholder> is the GUID of the package that provides <ui>Toolbox</ui> items.\</caps:sentence>
          </para>
          <para>
            \<caps:sentence id="src37" class="srcSentence">This Toolbox subkey must contain at least one entry, a DWORD entry named <placeholder>Default</placeholder><placeholder>Items</placeholder>.\</caps:sentence>
          </para>
          <alert class="note">
            <para>
              \<caps:sentence id="src38" class="srcSentence">The root path of HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\<placeholder>&lt;Version&gt;</placeholder> can be overridden with an alternate root when the Visual Studio shell is initialized, or you can use <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.DefaultRegistryRootAttribute</codeEntityReference>.\</caps:sentence>
              \<caps:sentence id="src39" class="srcSentence"> For more information, see \<link xlink:href="0a22516f-f60e-4476-ac5b-f41e5ffaaf8b">Command-Line Switches (VS SDK)</link>.\</caps:sentence>
            </para>
          </alert>
          <para>
            \<caps:sentence id="src40" class="srcSentence">For the entry under HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\<placeholder>&lt;Version&gt;</placeholder>\Packages\<placeholder>&lt;Package GUID</placeholder>&gt;:\</caps:sentence>
          </para>
          <table>
            <thead>
              <tr>
                <TD>
                  <para>
                    \<caps:sentence id="src41" class="srcSentence">Name\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence id="src42" class="srcSentence">Type\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence id="src43" class="srcSentence">Data\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence id="src44" class="srcSentence">Description\</caps:sentence>
                  </para>
                </TD>
              </tr>
            </thead>
            <tbody>
              <tr>
                <TD>
                  <para>
                    <userInput>Default Items</userInput>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence id="src45" class="srcSentence">REG_DWORD\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence id="src46" class="srcSentence">Can be any DWORD value.\</caps:sentence>
                    \<caps:sentence id="src47" class="srcSentence"> Starting with 1.\</caps:sentence>
                    \<caps:sentence id="src48" class="srcSentence"> The value is incremented if you update your VSPackage to supply more or different items.\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence id="src49" class="srcSentence">The value of <userInput>Default Items</userInput> must be greater than or equal to 1 to add <codeEntityReference autoUpgrade="true">T:System.Drawing.Design.ToolboxItem</codeEntityReference> objects to the <token>vsprvs</token> <ui>Toolbox</ui>.\</caps:sentence>
                  </para>
                  <para>
                    \<caps:sentence id="src50" class="srcSentence">Changing the value of <userInput>Default Items</userInput> will cause the <token>vsprvs</token> IDE to load the most recent instance of a VSPackage providing <codeEntityReference autoUpgrade="true">T:System.Drawing.Design.ToolboxItem</codeEntityReference> objects, rather than using any cached values.\</caps:sentence>
                  </para>
                  <para>
                    \<caps:sentence id="src51" class="srcSentence">In the Managed Package Framework, <userInput>Default Items</userInput> is set by the value used in the constructor for the <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.ProvideToolboxItemsAttribute</codeEntityReference> instance applied to the VSPackage providing <codeEntityReference autoUpgrade="true">T:System.Drawing.Design.ToolboxItem</codeEntityReference> objects.\</caps:sentence>
                  </para>
                </TD>
              </tr>
            </tbody>
          </table>
        </content>
      </section>
      <section>
        <title>
          \<caps:sentence id="src52" class="srcSentence">Registering Support for a Non-Standard Format\</caps:sentence>
        </title>
        <content>
          <para>
            \<caps:sentence id="src53" class="srcSentence">Registration of supported Clipboard formats that a <codeEntityReference autoUpgrade="true">T:System.Drawing.Design.ToolboxItem</codeEntityReference> provider VSPackage supports is optional.\</caps:sentence>
          </para>
          <para>
            \<caps:sentence id="src54" class="srcSentence">If a <codeEntityReference autoUpgrade="true">T:System.Drawing.Design.ToolboxItem</codeEntityReference> provider VSPackage does not register any special Clipboard formats, it must support the <token>vsprvs</token> standard formats.\</caps:sentence>
            \<caps:sentence id="src55" class="srcSentence"> For more information on the standard <ui>Toolbox</ui> Clipboard formats, see \<link xlink:href="bb84a79e-cd4c-4a58-8871-2513e7119b6e">Toolbox Overview</link>.\</caps:sentence>
          </para>
          <para>
            \<caps:sentence id="src56" class="srcSentence">If a VSPackage does provide support for non-standard formats, it must register those formats under the VSPackage's <ui>Toolbox</ui> registration key HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\<placeholder>&lt;Version&gt;</placeholder>\Packages\<placeholder>&lt;Package GUID</placeholder>&gt;\Toolbox, by adding a string entry named <userInput>Formats</userInput>.\</caps:sentence>
          </para>
          <alert class="note">
            <para>
              \<caps:sentence id="src57" class="srcSentence">If a VSPackage registers support for any custom format, it only supports those formats that it explicitly registers.\</caps:sentence>
              \<caps:sentence id="src58" class="srcSentence"> A VSPackage registering custom Clipboard formats is no longer registered as supporting the default <ui>Toolbox</ui> Clipboard formats, unless it does so explicitly.\</caps:sentence>
            </para>
          </alert>
          <table>
            <thead>
              <tr>
                <TD>
                  <para>
                    \<caps:sentence id="src59" class="srcSentence">Name\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence id="src60" class="srcSentence">Type\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence id="src61" class="srcSentence">Data\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence id="src62" class="srcSentence">Description\</caps:sentence>
                  </para>
                </TD>
              </tr>
            </thead>
            <tbody>
              <tr>
                <TD>
                  <para>
                    <userInput>Formats</userInput>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence id="src63" class="srcSentence">REG_SZ\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence id="src64" class="srcSentence">For custom formats, use a string for this subkey.\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence id="src65" class="srcSentence">Specifies the Clipboard formats supported by a VSPackage providing custom <ui>Toolbox</ui> Clipboard formats (by implementing <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.Interop.IVsToolboxDataProvider</codeEntityReference> and <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.Interop.IVsToolboxDataProvider2</codeEntityReference>).\</caps:sentence>
                  </para>
                  <para>
                    \<caps:sentence id="src66" class="srcSentence">The formats should be specified in a comma-separated list.\</caps:sentence>
                  </para>
                  <para>
                    \<caps:sentence id="src67" class="srcSentence">A format can be specified either by a string containing its name, or its ID name.\</caps:sentence>
                    \<caps:sentence id="src68" class="srcSentence"> For example, a <codeInline>Formats</codeInline> entry might be <codeInline>'1,13,16,HTML Format'</codeInline>.\</caps:sentence>
                  </para>
                  <para>
                    \<caps:sentence id="src69" class="srcSentence">For more information about Clipboard formats, see <codeEntityReference autoUpgrade="true">T:System.Windows.Forms.DataFormats.Format</codeEntityReference>.\</caps:sentence>
                  </para>
                  <para>
                    \<caps:sentence id="src70" class="srcSentence">In the Managed Package Framework, the value of <userInput>Formats</userInput> is obtained from the string used as an argument to the constructor for the instance of the <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.ProvideToolboxFormatAttribute</codeEntityReference> object applied to the VSPackage providing <codeEntityReference autoUpgrade="true">T:System.Drawing.Design.ToolboxItem</codeEntityReference> objects.\</caps:sentence>
                  </para>
                </TD>
              </tr>
            </tbody>
          </table>
        </content>
      </section>
      <section>
        <title>
          \<caps:sentence id="src71" class="srcSentence">Registering Support for Dynamic Toolbox-Item Configuration\</caps:sentence>
        </title>
        <content>
          <para>
            \<caps:sentence id="src72" class="srcSentence">If a VSPackage provides an implementation of <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.IConfigureToolboxItem</codeEntityReference> it must add registry settings under HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\<placeholder>&lt;Version&gt;</placeholder>\CLSID.\</caps:sentence>
            \<caps:sentence id="src73" class="srcSentence"> and HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\<placeholder>&lt;Version&gt;</placeholder>\ToolboxItemConfiguration.\</caps:sentence>
          </para>
          <para>
            \<caps:sentence id="src74" class="srcSentence">The registry data under HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\<placeholder>&lt;Version&gt;</placeholder>\CLSID contains the information the <token>vsprvs</token> environment requires to invoke the implementation of <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.IConfigureToolboxItem</codeEntityReference>.\</caps:sentence>
          </para>
          <para>
            \<caps:sentence id="src75" class="srcSentence">The HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\<placeholder>&lt;Version&gt;</placeholder>\ToolboxItemConfiguration data is used to select or filter which <codeEntityReference autoUpgrade="true">T:System.Drawing.Design.ToolboxItem</codeEntityReference> objects the implementation of <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.IConfigureToolboxItem</codeEntityReference> configures on the basis of the assemblies that contain them.\</caps:sentence>
          </para>
          <para>
            \<caps:sentence id="src76" class="srcSentence">Content of the HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\<placeholder>&lt;Version&gt;</placeholder>\CLSID Registry Entry:\</caps:sentence>
          </para>
          <alert class="note">
            <para>
              \<caps:sentence id="src77" class="srcSentence">Under the Managed Package Framework, these registry entries are created by the instance of <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.ProvideToolboxItemConfigurationAttribute</codeEntityReference>.\</caps:sentence>
              \<caps:sentence id="src78" class="srcSentence"> This instance is attached to the VSPackage that provides <codeEntityReference autoUpgrade="true">T:System.Drawing.Design.ToolboxItem</codeEntityReference> configuration by using reflection.\</caps:sentence>
              \<caps:sentence id="src79" class="srcSentence"> The reflection is performed on the <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.IConfigureToolboxItem</codeEntityReference> item that is provided to the <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.ProvideToolboxItemConfigurationAttribute</codeEntityReference> constructor.\</caps:sentence>
            </para>
          </alert>
          <table>
            <thead>
              <tr>
                <TD>
                  <para>
                    \<caps:sentence id="src80" class="srcSentence">Name\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence id="src81" class="srcSentence">Type\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence id="src82" class="srcSentence">Data\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence id="src83" class="srcSentence">Description\</caps:sentence>
                  </para>
                </TD>
              </tr>
            </thead>
            <tbody>
              <tr>
                <TD>
                  <para>
                    <placeholder>
                      \<caps:sentence id="src84" class="srcSentence">(Default)\</caps:sentence>
                    </placeholder>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence id="src85" class="srcSentence">REG_SZ\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence id="src86" class="srcSentence">(Optional)\</caps:sentence>
                  </para>
                  <para>
                    \<caps:sentence id="src87" class="srcSentence">Full name of the class implementing <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.IConfigureToolboxItem</codeEntityReference>.\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence id="src88" class="srcSentence">The value here should be the same as that provided by <codeEntityReference autoUpgrade="true">P:System.Type.FullName</codeEntityReference> acting on the <codeEntityReference autoUpgrade="true">T:System.Type</codeEntityReference> implementing <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.IConfigureToolboxItem</codeEntityReference>.\</caps:sentence>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <userInput>Assembly</userInput>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence id="src89" class="srcSentence">REG_SZ\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence id="src90" class="srcSentence">Full Name of the assembly providing the <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.IConfigureToolboxItem</codeEntityReference>\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence id="src91" class="srcSentence">This value must be the full assembly identification, which, depending on the assembly, may include:\</caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        \<caps:sentence id="src92" class="srcSentence">a simple name\</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        \<caps:sentence id="src93" class="srcSentence">a version number\</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        \<caps:sentence id="src94" class="srcSentence">a cryptographic key pair\</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        \<caps:sentence id="src95" class="srcSentence">a supported culture \</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        \<caps:sentence id="src96" class="srcSentence">a custom field\</caps:sentence>
                      </para>
                    </listItem>
                  </list>
                  <para>
                    \<caps:sentence id="src97" class="srcSentence">The value must be a comma-separated list of property values as would be provided by <codeEntityReference autoUpgrade="true">P:System.Type.FullName</codeEntityReference> property acting on the <codeEntityReference autoUpgrade="true">T:System.Type</codeEntityReference> implementing <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.IConfigureToolboxItem</codeEntityReference>.\</caps:sentence>
                  </para>
                  <para>
                    \<caps:sentence id="src98" class="srcSentence">For instance:\</caps:sentence>
                  </para>
                  <code>MyPackage.Toolbox, Version=8.0.1200.0, Culture=neutral,PublicKeyToken=abcdef12345ab, Custom=null</code>
                  <para>
                    \<caps:sentence id="src99" class="srcSentence">Wildcard characters are not supported.\</caps:sentence>
                  </para>
                  <para>
                    \<caps:sentence id="src100" class="srcSentence">For more information on the format of full assembly names, see <codeEntityReference autoUpgrade="true">P:System.Type.AssemblyQualifiedName</codeEntityReference>.\</caps:sentence>
                  </para>
                  <para>
                    \<caps:sentence id="src101" class="srcSentence">
                      <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.IConfigureToolboxItem</codeEntityReference>.\</caps:sentence>
                  </para>
                  <para>
                    \<caps:sentence id="src102" class="srcSentence">For more information on assembly identification, see <codeEntityReference autoUpgrade="true">T:System.Reflection.AssemblyName</codeEntityReference>.\</caps:sentence>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <userInput>Class</userInput>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence id="src103" class="srcSentence">REG_SZ\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence id="src104" class="srcSentence">Full name of the class implementing the <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.IConfigureToolboxItem</codeEntityReference> interface as provided by <codeEntityReference autoUpgrade="true">P:System.Type.FullName</codeEntityReference>.\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence id="src105" class="srcSentence">The value should be the same as that provided by <codeEntityReference autoUpgrade="true">P:System.Type.FullName</codeEntityReference>, acting on the type implementing <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.IConfigureToolboxItem</codeEntityReference>.\</caps:sentence>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <userInput>CodeBase</userInput>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence id="src106" class="srcSentence">REG_SZ\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence id="src107" class="srcSentence">Location of the assembly providing the implementation of <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.IConfigureToolboxItem</codeEntityReference>\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence id="src108" class="srcSentence">This value must be the fully qualified path to the assembly file containing the implementation of <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.IConfigureToolboxItem</codeEntityReference>.\</caps:sentence>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <userInput>InprocServer32</userInput>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence id="src109" class="srcSentence">REG_SZ\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence id="src110" class="srcSentence">Must always be set to <codeInline>"C:\WINDOWS\System32\mscoree.dll"</codeInline>\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence id="src111" class="srcSentence">The in-process server\</caps:sentence>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <userInput>ThreadingModel</userInput>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence id="src112" class="srcSentence">REG_SZ\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence id="src113" class="srcSentence">Must always be set to <codeInline>"Both"</codeInline>\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence id="src114" class="srcSentence">Threading model\</caps:sentence>
                  </para>
                </TD>
              </tr>
            </tbody>
          </table>
          <para>
            \<caps:sentence id="src115" class="srcSentence">Content of the HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\<placeholder>&lt;Version&gt;</placeholder>\ToolboxItemConfiguration Registry Entry:\</caps:sentence>
          </para>
          <alert class="note">
            <para>
              \<caps:sentence id="src116" class="srcSentence">Under the Managed Package Framework, these registry entries are created by the instance of <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.ProvideAssemblyFilterAttribute</codeEntityReference> attached to the <codeEntityReference autoUpgrade="true">T:System.Type</codeEntityReference> providing an implementation of <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.IConfigureToolboxItem</codeEntityReference>.\</caps:sentence>
            </para>
          </alert>
          <table>
            <thead>
              <tr>
                <TD>
                  <para>
                    \<caps:sentence id="src117" class="srcSentence">Name\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence id="src118" class="srcSentence">Type\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence id="src119" class="srcSentence">Data\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence id="src120" class="srcSentence">Description\</caps:sentence>
                  </para>
                </TD>
              </tr>
            </thead>
            <tbody>
              <tr>
                <TD>
                  <para>
                    <placeholder>
                      \<caps:sentence id="src121" class="srcSentence">&lt;AssemblyName&gt;\</caps:sentence>
                    </placeholder>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence id="src122" class="srcSentence">REG_SZ\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence id="src123" class="srcSentence">Specification of the assemblies to select or filter.\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence id="src124" class="srcSentence">The key's name, <placeholder>&lt;AssemblyName&gt;</placeholder>, must be specified in the format of full assembly identification, which, depending on the assemblies to be filtered, may include:\</caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        \<caps:sentence id="src125" class="srcSentence">a simple name\</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        \<caps:sentence id="src126" class="srcSentence">a version number\</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        \<caps:sentence id="src127" class="srcSentence">a cryptographic key pair\</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        \<caps:sentence id="src128" class="srcSentence">a supported culture \</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        \<caps:sentence id="src129" class="srcSentence">a custom field\</caps:sentence>
                      </para>
                    </listItem>
                  </list>
                  <para>
                    \<caps:sentence id="src130" class="srcSentence">The key's name must be a comma-separated list of property value pairs.\</caps:sentence>
                    \<caps:sentence id="src131" class="srcSentence"> For more information on the format of full assembly names, see the <codeEntityReference qualifyHint="true" autoUpgrade="true">P:System.Type.FullName</codeEntityReference> property.\</caps:sentence>
                  </para>
                  <para>
                    \<caps:sentence id="src132" class="srcSentence">A wildcard character of <codeInline>"*"</codeInline> is supported in this value, and any field not provided is treated as a wildcard.\</caps:sentence>
                  </para>
                  <para>
                    \<caps:sentence id="src133" class="srcSentence">For instance, a key name of \</caps:sentence>
                  </para>
                  <code>System.Windows.*, Version=8.0.*, Culture=*,PublicKeyToken=*</code>
                  <para>
                    \<caps:sentence id="src134" class="srcSentence">selects all assemblies with namespaces under <codeInline>System.Windows</codeInline> (though not <codeInline>System.Windows</codeInline> itself), for all minor versions of the 8.0 release, and for all cultures, cryptographic key values, and custom strings.\</caps:sentence>
                  </para>
                  <para>
                    \<caps:sentence id="src135" class="srcSentence">In the Managed Package Framework, the <placeholder>&lt;Assembly Name&gt;</placeholder> key's name is determined by the string used as the argument to the constructor for the <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.ProvideAssemblyFilterAttribute</codeEntityReference>  instance applied to the class implementing the <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.IConfigureToolboxItem</codeEntityReference> interface.\</caps:sentence>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <placeholder>
                      \<caps:sentence id="src136" class="srcSentence">&lt;ImplementationObject&gt;\</caps:sentence>
                    </placeholder>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence id="src137" class="srcSentence">REG_SZ\</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence id="src138" class="srcSentence">GUID \</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    \<caps:sentence id="src139" class="srcSentence">The name of this subkey of <placeholder>AssemblyName</placeholder> is the fully qualified name of the <codeEntityReference autoUpgrade="true">T:System.Type</codeEntityReference> implementing the <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.IConfigureToolboxItem</codeEntityReference> interface.\</caps:sentence>
                  </para>
                  <para>
                    \<caps:sentence id="src140" class="srcSentence">The value of this subkey is the GUID of this <codeEntityReference autoUpgrade="true">T:System.Type</codeEntityReference>.\</caps:sentence>
                  </para>
                  <para>
                    \<caps:sentence id="src141" class="srcSentence">In the Managed Package Framework this information is obtained through reflection from the class implementing the <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.IConfigureToolboxItem</codeEntityReference> interface with a <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.ProvideAssemblyFilterAttribute</codeEntityReference> object applied to it.\</caps:sentence>
                  </para>
                </TD>
              </tr>
            </tbody>
          </table>
          <para>
            \<caps:sentence id="src142" class="srcSentence">An example of an entry under HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\<placeholder>&lt;Version&gt;</placeholder>\ToolboxItemConfiguration would be:\</caps:sentence>
          </para>
          <para>
            <codeInline>        Vsip.*, Version=2.0.3500</codeInline>
          </para>
          <para>
            <codeInline>            Vsip.ToolboxConfiguration = {YYYYYYYY-YYYY-YYYY-YYYY-YYYYYYYYYYYY}</codeInline>
          </para>
        </content>
      </section>
      <relatedTopics>
        \<link xlink:href="3b052047-f6db-46dd-b3bf-da1c348ee410">Managing the Toolbox</link>
        \<link xlink:href="c3e8b404-7086-4e08-9d07-ab9c509963ca">How To: Provide Custom Toolbox Items Using Interop Assemblies</link>
        <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.ProvideToolboxItemsAttribute</codeEntityReference>
        <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.ProvideToolboxFormatAttribute</codeEntityReference>
        <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.ProvideAssemblyFilterAttribute</codeEntityReference>
        <codeEntityReference autoUpgrade="true">T:Microsoft.VisualStudio.Shell.IConfigureToolboxItem</codeEntityReference>
        <codeEntityReference autoUpgrade="true">T:System.Drawing.Design.ToolboxItem</codeEntityReference>
      </relatedTopics>
    </developerConceptualDocument>
  \</caps:SxSSource>
\</caps:SxS>