# Desafio de projeto DIO

Neste desafio, foi modelado e diagramado a representação UML do componente Smartphone, abrangendo suas funcionalidades como Reprodutor Musical, Aparelho Telefônico e Navegador na Internet.

## UML

```mermaid
classDiagram
    Smartphone o--> MusicPlayer
    Smartphone o--> TelephoneDevice
    Smartphone o--> InternetBrowser
    Smartphone o--> Calendar
    Smartphone o--> Camera
    Smartphone o--> Notes
    Smartphone : -MusicPlayer musicPlayer
    Smartphone : -TelephoneDevice telephoneDevice
    Smartphone : -InternetBrowser internetBrowser
    Smartphone : -Calendar calendar
    Smartphone : -Camera camera
    Smartphone : -Notes notes
    Smartphone: +accessMusicPlayer() MusicPlayer
    Smartphone: +accessTelephoneDevice() TelephoneDevice
    Smartphone: +accessInternetBrowser() InternetBrowser
    Smartphone: +accessCalendar() Calendar
    Smartphone: +accessCamera() Camera
    Smartphone: +accessNotes() Notes

    class MusicPlayer{
        -playlist: List~Song~
        -currentSong: Song
        -state: SongState
        -repeat: Boolean
        -random: Boolean
        -elapsedTime: LocalTime
        -remainingTime: LocalTime
        -volume: Integer
        +play() void
        +pause() void
        +next() void
        +back() void
        +selectSong(String song) void
        +toggleRepeat() void
        +toggleRandom() void
        +increaseVolume() void
        +decreaseVolume() void
    }
    class TelephoneDevice{
        -contacts: List~Contact~
        -callLog: List~Call~
        -signalState: SignalEnum
        +call(String number) void
        +answerCall() void
        +startVoiceMail() void
        +showContactList() List~Contact~
        +addContact(Contact contact)
        +removeContact(String contactId)
        +showCallLog() List~Call~
        +getSignalState() SignalEnum
    }
    class InternetBrowser{
        -url: String
        -currentPage: String
        -favorites: List~String~
        -browsingHistory: List~String~
        +home() String
        +navigate(String url) String
        +openNewTab() void
        +reloadPage() String
        +stopLoad() void
        +next() String
        +back() String
        +getFavorites() List~String~
        +addFavorite(String url) void
        +removeFavorite(String url) void
        +getBrowsingHistory() List~String~
    }
    class Calendar{
        -currentDate: LocalDate
        +getCurrentDate() LocalDate
        +showCalendar() CalendarView
        -updateCurrentDate() void
    }
    class Camera{
        -gallery: List~Photo~
        -lastPhoto: Photo
        +takePhoto() Photo
        +showGallery() List~Photo~
    }
    class Notes{
        -notes: List~Note~
        +addNote(Note note) Note
        +removeNote(Note note) void
        +updateNote(Note note) Note
        +getNotes() List~Note~
        +addFavorite(String noteId) void
    }
```
