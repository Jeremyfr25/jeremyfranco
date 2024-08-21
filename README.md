import { HttpClientModule } from '@angular/common/http';

@NgModule({
  declarations: [
    // tus componentes
  ],
  imports: [
    HttpClientModule,
    // otros módulos
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }


import { Injectable } from '@angular/core';
import { HttpClient } from '@angular/common/http';
import { Observable } from 'rxjs';

@Injectable({
  providedIn: 'root'
})
export class ApiService {

  private apiUrl = 'https://api.example.com'; // Cambia esta URL por la de tu API

  constructor(private http: HttpClient) { }

  getData(): Observable<any> {
    return this.http.get(`${this.apiUrl}/endpoint`);
  }

  postData(data: any): Observable<any> {
    return this.http.post(`${this.apiUrl}/endpoint`, data);
  }

  // Otros métodos para PUT, DELETE, etc.
}
