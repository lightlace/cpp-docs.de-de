---
title: Windows-Vorgänge (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- Windows [C++], Windows-specific tasks
- .NET Framework [C++], Windows operations
- Visual C++, Windows operations
- Windows operations [C++]
- .NET Framework, shutdown
- shutdown
- termination
- applications [C++], shutdown
- Visual C++, user interactive state
- user interactive state
- Visual C++, reading from Windows Registry
- registry, reading
- performance counters
- performance counters, reading Windows performance counters
- performance monitoring, Windows performance counters
- performance, counters
- counters, reading Windows performance counters
- performance
- performance monitoring
- text, retrieving from Clipboard
- Clipboard, retrieving text
- current user names
- user names, retrieving
- UserName string
- .NET Framework, version
- Version property, retrieving .NET Framework version
- computer name, retrieving
- machine name, retrieving
- computer name
- Windows [C++], version
- Windows [C++], retrieving version using Visual C++
- time, elapsed since startup
- counters, elapsed time
- startup, time elapsed since
- tick counts
- startup
- text, storing in Clipboard
- Clipboard, storing text
- registry, writing to
- Visual C++, writing to Windows Registry
ms.assetid: b9a75cb4-0589-4d5b-92cb-5e8be42b4ac0
ms.openlocfilehash: 413ccc3b66d76f8779861d4d65eb262ee8640725
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62384373"
---
# <a name="windows-operations-ccli"></a>Windows-Vorgänge (C++/CLI)

Veranschaulicht verschiedene Windows-spezifische Aufgaben, die mit dem Windows SDK.

In den folgenden Themen veranschaulichen die verschiedenen Windows-Operationen mit dem Windows SDK, die mit Visual C++.

## <a name="determine_shutdown"></a> Bestimmt, ob das Herunterfahren begonnen hat

Im folgenden Codebeispiel wird veranschaulicht, zu bestimmen, ob die Anwendung oder .NET Framework gerade beendet wird. Dies ist nützlich für den Zugriff auf statische Elemente in .NET Framework, da während des Herunterfahrens können diese Konstrukte durch das System beendet werden und können nicht zuverlässig verwendet werden kann. Durch Überprüfen der <xref:System.Environment.HasShutdownStarted%2A> Eigenschaft zunächst können Sie potenzielle Fehler vermeiden, indem Sie nicht auf diese Elemente zugreifen.

### <a name="example"></a>Beispiel

```cpp
// check_shutdown.cpp
// compile with: /clr
using namespace System;
int main()
{
   if (Environment::HasShutdownStarted)
      Console::WriteLine("Shutting down.");
   else
      Console::WriteLine("Not shutting down.");
   return 0;
}
```

## <a name="determine_user"></a> Ermitteln des interaktiven Zustands

Im folgenden Codebeispiel wird veranschaulicht, zu bestimmen, ob der Code in einem interaktiven Kontext ausgeführt wird. Wenn <xref:System.Environment.UserInteractive%2A> ist "false", und klicken Sie dann der Code als ein Dienstprozess ausgeführt wird, oder aus in einer Webanwendung, in diesem Fall Sie nicht versuchen sollten, mit dem Benutzer interagieren.

### <a name="example"></a>Beispiel

```cpp
// user_interactive.cpp
// compile with: /clr
using namespace System;

int main()
{
   if ( Environment::UserInteractive )
      Console::WriteLine("User interactive");
   else
      Console::WriteLine("Noninteractive");
   return 0;
}
```

## <a name="read_registry"></a> Lesen von Daten aus der Windows-Registrierung

Im folgenden Codebeispiel wird der <xref:Microsoft.Win32.Registry.CurrentUser>-Schlüssel verwendet, um Daten aus der Windows-Registrierung zu lesen. Zunächst werden die Unterschlüssel mit aufgelistet der <xref:Microsoft.Win32.RegistryKey.GetSubKeyNames%2A> -Methode, und klicken Sie dann der Identities-Unterschlüssel mit geöffnet wird die <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A> Methode. Jeder Unterschlüssel wird wie ein Stammschlüssel durch die <xref:Microsoft.Win32.RegistryKey>-Klasse dargestellt. Schließlich werden mit dem neuen <xref:Microsoft.Win32.RegistryKey>-Objekt die Schlüssel/Wert-Paare aufgelistet.

### <a name="example"></a>Beispiel

```cpp
// registry_read.cpp
// compile with: /clr
using namespace System;
using namespace Microsoft::Win32;

int main( )
{
   array<String^>^ key = Registry::CurrentUser->GetSubKeyNames( );

   Console::WriteLine("Subkeys within CurrentUser root key:");
   for (int i=0; i<key->Length; i++)
   {
      Console::WriteLine("   {0}", key[i]);
   }

   Console::WriteLine("Opening subkey 'Identities'...");
   RegistryKey^ rk = nullptr;
   rk = Registry::CurrentUser->OpenSubKey("Identities");
   if (rk==nullptr)
   {
      Console::WriteLine("Registry key not found - aborting");
      return -1;
   }

   Console::WriteLine("Key/value pairs within 'Identities' key:");
   array<String^>^ name = rk->GetValueNames( );
   for (int i=0; i<name->Length; i++)
   {
      String^ value = rk->GetValue(name[i])->ToString();
      Console::WriteLine("   {0} = {1}", name[i], value);
   }

   return 0;
}
```

### <a name="remarks"></a>Hinweise

Die <xref:Microsoft.Win32.Registry>-Klasse ist lediglich ein Container für statische Instanzen von <xref:Microsoft.Win32.RegistryKey>. Jede Instanz stellt einen Stammregistrierungsknoten dar. Die Instanzen sind <xref:Microsoft.Win32.Registry.ClassesRoot>, <xref:Microsoft.Win32.Registry.CurrentConfig>, <xref:Microsoft.Win32.Registry.CurrentUser>, <xref:Microsoft.Win32.Registry.LocalMachine> und <xref:Microsoft.Win32.Registry.Users>.

Die Objekte innerhalb der <xref:Microsoft.Win32.Registry>-Klasse sind nicht nur statisch, sondern auch schreibgeschützt. Darüber hinaus sind Instanzen der <xref:Microsoft.Win32.RegistryKey>-Klasse, die für den Zugriff auf den Inhalt der Registrierungsobjekte erstellt wurden, ebenfalls schreibgeschützt. Ein Beispiel zum Überschreiben dieses Verhaltens finden Sie unter [Vorgehensweise: Schreiben von Daten in der Windows-Registrierung (C++ / CLI)](../dotnet/how-to-write-data-to-the-windows-registry-cpp-cli.md).

In der <xref:Microsoft.Win32.Registry>-Klasse stehen zwei weitere Objekte zur Verfügung: <xref:Microsoft.Win32.Registry.DynData> und <xref:Microsoft.Win32.Registry.PerformanceData>. Bei beiden Objekten handelt es sich um Instanzen der <xref:Microsoft.Win32.RegistryKey>-Klasse. Die <xref:Microsoft.Win32.Registry.DynData> -Objekt enthält dynamische Registrierungsinformationen, die nur unter Windows 98 und Windows Me unterstützt wird Das <xref:Microsoft.Win32.Registry.PerformanceData>-Objekt dient dem Zugriff auf Informationen zu Leistungsindikatoren für Anwendungen, die das Leistungsüberwachungssystem von Windows verwenden. Die <xref:Microsoft.Win32.Registry.PerformanceData> Knoten enthält Informationen, die eigentlich nicht in der Registrierung gespeichert und daher nicht mit Regedit.exe angezeigt werden können.

## <a name="read_performance"></a> Lesen von Windows-Leistungsindikatoren

Einige Anwendungen und Windows-Subsysteme verfügbar machen Leistungsdaten über die Windows-Leistung-System. Diese Leistungsindikatoren können zugegriffen werden, mithilfe der <xref:System.Diagnostics.PerformanceCounterCategory> und <xref:System.Diagnostics.PerformanceCounter> Klassen, die in befinden die <xref:System.Diagnostics?displayProperty=fullName> Namespace.

Im folgenden Codebeispiel verwendet diese Klassen zum Abrufen und Anzeigen von einen Indikator, der aktualisiert wird, indem Windows an, dass der Prozentsatz der Zeit, die der Prozessor ausgelastet ist.

> [!NOTE]
>  Für dieses Beispiel benötigen Sie Administratorrechte, um es unter Windows Vista auszuführen.

### <a name="example"></a>Beispiel

```cpp
// processor_timer.cpp
// compile with: /clr
#using <system.dll>

using namespace System;
using namespace System::Threading;
using namespace System::Diagnostics;
using namespace System::Timers;

ref struct TimerObject
{
public:
   static String^ m_instanceName;
   static PerformanceCounter^ m_theCounter;

public:
   static void OnTimer(Object^ source, ElapsedEventArgs^ e)
   {
      try
      {
         Console::WriteLine("CPU time used: {0,6} ",
          m_theCounter->NextValue( ).ToString("f"));
      }
      catch(Exception^ e)
      {
         if (dynamic_cast<InvalidOperationException^>(e))
         {
            Console::WriteLine("Instance '{0}' does not exist",
                  m_instanceName);
            return;
         }
         else
         {
            Console::WriteLine("Unknown exception... ('q' to quit)");
            return;
         }
      }
   }
};

int main()
{
   String^ objectName = "Processor";
   String^ counterName = "% Processor Time";
   String^ instanceName = "_Total";

   try
   {
      if ( !PerformanceCounterCategory::Exists(objectName) )
      {
         Console::WriteLine("Object {0} does not exist", objectName);
         return -1;
      }
   }
   catch (UnauthorizedAccessException ^ex)
   {
      Console::WriteLine("You are not authorized to access this information.");
      Console::Write("If you are using Windows Vista, run the application with ");
      Console::WriteLine("administrative privileges.");
      Console::WriteLine(ex->Message);
      return -1;
   }

   if ( !PerformanceCounterCategory::CounterExists(
          counterName, objectName) )
   {
      Console::WriteLine("Counter {0} does not exist", counterName);
      return -1;
   }

   TimerObject::m_instanceName = instanceName;
   TimerObject::m_theCounter = gcnew PerformanceCounter(
          objectName, counterName, instanceName);

   System::Timers::Timer^ aTimer = gcnew System::Timers::Timer();
   aTimer->Elapsed += gcnew ElapsedEventHandler(&TimerObject::OnTimer);
   aTimer->Interval = 1000;
   aTimer->Enabled = true;
   aTimer->AutoReset = true;

   Console::WriteLine("reporting CPU usage for the next 10 seconds");
   Thread::Sleep(10000);
   return 0;
}
```

## <a name="retrieve_text"></a> Abrufen von Text aus der Zwischenablage

Im folgenden Codebeispiel wird die <xref:System.Windows.Forms.Clipboard.GetDataObject%2A> Member-Funktion zur Rückgabe eines Zeigers auf die <xref:System.Windows.Forms.IDataObject> Schnittstelle. Diese Schnittstelle kann dann abgefragt, die für das Format der Daten und verwendet, um die eigentlichen Daten abzurufen.

### <a name="example"></a>Beispiel

```cpp
// read_clipboard.cpp
// compile with: /clr
#using <system.dll>
#using <system.Drawing.dll>
#using <system.windows.forms.dll>

using namespace System;
using namespace System::Windows::Forms;

[STAThread] int main( )
{
   IDataObject^ data = Clipboard::GetDataObject( );

   if (data)
   {
      if (data->GetDataPresent(DataFormats::Text))
      {
         String^ text = static_cast<String^>
           (data->GetData(DataFormats::Text));
         Console::WriteLine(text);
      }
      else
         Console::WriteLine("Nontext data is in the Clipboard.");
   }
   else
   {
      Console::WriteLine("No data was found in the Clipboard.");
   }

   return 0;
}
```

## <a name="retrieve_current"></a> Abrufen des aktuellen Benutzernamens

Das folgende Codebeispiel veranschaulicht das Abrufen des aktuellen Benutzernamens (der Name des Benutzers bei Windows angemeldet ist). Der Name befindet sich in der <xref:System.Environment.UserName%2A> Zeichenfolge, die in definierten die <xref:System.Environment> Namespace.

### <a name="example"></a>Beispiel

```cpp
// username.cpp
// compile with: /clr
using namespace System;

int main()
{
   Console::WriteLine("\nCurrent user: {0}", Environment::UserName);
   return 0;
}
```

## <a name="retrieve_dotnet"></a> Abrufen der .NET Framework-Version

Im folgenden Codebeispiel wird veranschaulicht, wie zum Ermitteln der Version der installierten .NET Framework mit der <xref:System.Environment.Version%2A> -Eigenschaft, die ein Zeiger auf eine <xref:System.Version> Objekt, das die Versionsinformationen enthält.

### <a name="example"></a>Beispiel

```cpp
// dotnet_ver.cpp
// compile with: /clr
using namespace System;
int main()
{
   Version^ version = Environment::Version;
   if (version)
   {
      int build = version->Build;
      int major = version->Major;
      int minor = version->Minor;
      int revision = Environment::Version->Revision;
      Console::Write(".NET Framework version: ");
      Console::WriteLine("{0}.{1}.{2}.{3}",
            build, major, minor, revision);
   }
   return 0;
}
```

## <a name="retrieve_local"></a> Abrufen des lokalen Computernamens

Das folgende Codebeispiel veranschaulicht das Abrufen des lokalen Computernamens (in einem Netzwerk wird der Name des Computers, wie er angezeigt). Sie erreichen dies durch Abrufen der <xref:System.Environment.MachineName%2A> Zeichenfolge, die in definiert ist die <xref:System.Environment> Namespace.

### <a name="example"></a>Beispiel

```cpp
// machine_name.cpp
// compile with: /clr
using namespace System;

int main()
{
   Console::WriteLine("\nMachineName: {0}", Environment::MachineName);
   return 0;
}
```

## <a name="retrieve_version"></a> Rufen Sie die Windows-Version

Im folgenden Codebeispiel wird veranschaulicht, wie zum Abrufen der Plattform und-Version Informationen des aktuellen Betriebssystems wird. Diese Informationen werden gespeichert, der <xref:System.Environment.OSVersion%2A?displayProperty=fullName> Eigenschaft besteht aus einer Enumeration, die die Version von Windows im großen und ganzen beschreibt und <xref:System.Environment.Version%2A> -Objekt, das den genauen Build des Betriebssystems enthält.

### <a name="example"></a>Beispiel

```cpp
// os_ver.cpp
// compile with: /clr
using namespace System;

int main()
{
   OperatingSystem^ osv = Environment::OSVersion;
   PlatformID id = osv->Platform;
   Console::Write("Operating system: ");

   if (id == PlatformID::Win32NT)
      Console::WriteLine("Win32NT");
   else if (id == PlatformID::Win32S)
      Console::WriteLine("Win32S");
   else if (id == PlatformID::Win32Windows)
      Console::WriteLine("Win32Windows");
   else
      Console::WriteLine("WinCE");

   Version^ version = osv->Version;
   if (version)
   {
      int build = version->Build;
      int major = version->Major;
      int minor = version->Minor;
      int revision = Environment::Version->Revision;
      Console::Write("OS Version: ");
      Console::WriteLine("{0}.{1}.{2}.{3}",
                   build, major, minor, revision);
   }

   return 0;
}
```

## <a name="retrieve_time"></a> Abrufen der vergangenen Zeit seit dem Start

Im folgenden Codebeispiel wird veranschaulicht, um zu bestimmen, die Anzahl der Ticks, oder die Anzahl der Millisekunden, die seit Windows vergangen sind, wurde gestartet. Dieser Wert befindet sich in der <xref:System.Environment.TickCount%2A?displayProperty=fullName> Member und, da es sich um einen 32-Bit-Wert handelt, wird auf Null zurückgesetzt ungefähr alle 24,9 Tage.

### <a name="example"></a>Beispiel

```cpp
// startup_time.cpp
// compile with: /clr
using namespace System;

int main( )
{
   Int32 tc = Environment::TickCount;
   Int32 seconds = tc / 1000;
   Int32 minutes = seconds / 60;
   float hours = static_cast<float>(minutes) / 60;
   float days = hours / 24;

   Console::WriteLine("Milliseconds since startup: {0}", tc);
   Console::WriteLine("Seconds since startup: {0}", seconds);
   Console::WriteLine("Minutes since startup: {0}", minutes);
   Console::WriteLine("Hours since startup: {0}", hours);
   Console::WriteLine("Days since startup: {0}", days);

   return 0;
}
```

## <a name="store_text"></a> Store-Text in der Zwischenablage

Im folgenden Codebeispiel wird die <xref:System.Windows.Forms.Clipboard> Objekt definiert, der <xref:System.Windows.Forms> Namespace zum Speichern einer Zeichenfolge. Dieses Objekt stellt zwei Memberfunktionen: <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> und <xref:System.Windows.Forms.Clipboard.GetDataObject%2A>. Daten werden in der Zwischenablage gespeichert, per jedes Objekt abgeleitet <xref:System.Object> zu <xref:System.Windows.Forms.Clipboard.SetDataObject%2A>.

### <a name="example"></a>Beispiel

```cpp
// store_clipboard.cpp
// compile with: /clr
#using <System.dll>
#using <System.Drawing.dll>
#using <System.Windows.Forms.dll>

using namespace System;
using namespace System::Windows::Forms;

[STAThread] int main()
{
   String^ str = "This text is copied into the Clipboard.";

   // Use 'true' as the second argument if
   // the data is to remain in the clipboard
   // after the program terminates.
   Clipboard::SetDataObject(str, true);

   Console::WriteLine("Added text to the Clipboard.");

   return 0;
}
```

## <a name="write_data"></a> Schreiben von Daten in der Windows-Registrierung

Im folgenden Codebeispiel wird die <xref:Microsoft.Win32.Registry.CurrentUser> zu eine schreibbare Instanz der zu erstellenden Schlüssels, der <xref:Microsoft.Win32.RegistryKey> Klasse entspricht dem **Software** Schlüssel. Anschließend wird die <xref:Microsoft.Win32.RegistryKey.CreateSubKey%2A>-Methode verwendet, um einen neuen Schlüssel zu erstellen und Schlüssel/Wert-Paare hinzuzufügen.

### <a name="example"></a>Beispiel

```cpp
// registry_write.cpp
// compile with: /clr
using namespace System;
using namespace Microsoft::Win32;

int main()
{
   // The second OpenSubKey argument indicates that
   // the subkey should be writable.
   RegistryKey^ rk;
   rk  = Registry::CurrentUser->OpenSubKey("Software", true);
   if (!rk)
   {
      Console::WriteLine("Failed to open CurrentUser/Software key");
      return -1;
   }

   RegistryKey^ nk = rk->CreateSubKey("NewRegKey");
   if (!nk)
   {
      Console::WriteLine("Failed to create 'NewRegKey'");
      return -1;
   }

   String^ newValue = "NewValue";
   try
   {
      nk->SetValue("NewKey", newValue);
      nk->SetValue("NewKey2", 44);
   }
   catch (Exception^)
   {
      Console::WriteLine("Failed to set new values in 'NewRegKey'");
      return -1;
   }

   Console::WriteLine("New key created.");
   Console::Write("Use REGEDIT.EXE to verify ");
   Console::WriteLine("'CURRENTUSER/Software/NewRegKey'\n");
   return 0;
}
```

### <a name="remarks"></a>Hinweise

Sie können .NET Framework verwenden, um Zugriff auf die Registrierung mit der <xref:Microsoft.Win32.Registry> und <xref:Microsoft.Win32.RegistryKey> Klassen, die beide sind definiert, der <xref:Microsoft.Win32> Namespace. Die **Registrierung** Klasse ist ein Container für statische Instanzen von der <xref:Microsoft.Win32.RegistryKey> Klasse. Jede Instanz stellt einen Stammregistrierungsknoten dar. Die Instanzen sind <xref:Microsoft.Win32.Registry.ClassesRoot>, <xref:Microsoft.Win32.Registry.CurrentConfig>, <xref:Microsoft.Win32.Registry.CurrentUser>, <xref:Microsoft.Win32.Registry.LocalMachine> und <xref:Microsoft.Win32.Registry.Users>.

## <a name="related-sections"></a>Verwandte Abschnitte

<xref:System.Environment>

## <a name="see-also"></a>Siehe auch

[.NET-Programmierung mit C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
