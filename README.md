# String
一个String类

String operator + (const String & a,const String & b)
{
    int len = a.len+b.len;
    char* temp = new char[len+1];
    for (int i = 0; i<a.len; i++) {
        temp[i] = a.rep[i];
    }
    for (int i = 0; i<b.len; i++) {
        temp[i+a.len] = b.rep[i];
    }
    String str(temp);
    delete temp;
    return str;
}
String operator +=(const String& a)
{
    this->len += a.len;
    char* temp = this->rep;
    this->rep = new char[len+1];
    strcpy(this->rep, a.rep);
    strcat(this->rep, temp);
    delete temp;
    return *this;
}
String operator = (const String & a)
{
    if (this!=&a) {
        this->len=a.len;
        delete this->rep;
        this->rep=new char[a.len+1];
        strcpy(this->rep,a.rep);
    }
    return *this;
}
