This is an educational repository that contains homeworks, completed as part of Vadim Ksendzov's training course on software testing. Here I am learning how to work in Postman. Below is my homework and solution

# HW_2 Postman


## http:162.55.220.72:5005/first
 1. Отправить запрос.
 2. Статус **код 200**
``` js 
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```
 3. Проверить, что в **body** приходит правильный **string**.
``` bash 
pm.test("Body is the correct string", function () {
    pm.expect(pm.response.text()).to.include("This is the first responce from server!");
});
```
---


## http:162.55.220.72:5005/user_info_3
 1. Отправить запрос.
 2. Статус **код 200**
``` js 
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```
 3. Спарсить **response body в json**
``` js 
let jsonData = pm.response.json();
```
 4. Проверить, что **name в ответе равно name s request** (name вбить руками.)
``` js 
let name_s_request = 'Lena'
let name = jsonData.name
pm.test("Name check", function () {
        pm.expect(name).to.eql(name_s_request);
});
```
 5. Проверить, что **age в ответе равно age s request** (age вбить руками.)
 ``` js 
let age_s_request = '30'
let age = jsonData.age
pm.test("Age check", function () {
        pm.expect(age).to.eql(age_s_request);
});
```
 6. Проверить, что **salary в ответе равно salary s request** (salary вбить руками.)
 ``` js 
let salary_s_request = 1000
let salary = jsonData.salary
pm.test("Salary check", function () {
        pm.expect(salary).to.eql(salary_s_request);
});
```
 7. Спарсить **request**.
 ``` js 
let req = request.data
```
 8. Проверить, что **name в ответе равно name s request** (name забрать из request.)
 ``` js 
let name_request = req.name
pm.test("Name check2", function () {
        pm.expect(name).to.eql(name_request);
});
```
 9. Проверить, что **age в ответе равно age s request** (age забрать из request.)
 ``` js 
let age_request = req.age
pm.test("Age check2", function () {
        pm.expect(age).to.eql(age_request);
});
```
 10. Проверить, что **salary в ответе равно salary s request** (salary забрать из request.)
``` js 
let salary_request = req.salary
pm.test("Salary check2", function () {
        pm.expect(salary).to.eql(Number(salary_request));
});
```
 11. Вывести в консоль параметр **family из response**.
 ``` js 
let family = jsonData.family
console.log(family)
```
 12. Проверить что **u_salary_1_5_year в ответе равно salary*4** (salary забрать из request)
``` js 
let salary_1_5_year = req.salary * 4
let u_salary_1_5_year = jsonData.family.u_salary_1_5_year
pm.test("Salary_1_5_year check", function () {
        pm.expect(u_salary_1_5_year).to.eql(salary_1_5_year);
});
```

---


## http:162.55.220.72:5005/object_info_3
 1. Отправить запрос.
 2. Статус **код 200**
``` js 
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```
 3. Спарсить response **body в json**
``` js 
let jsonData = pm.response.json();
```
 4. Спарсить **request**.
``` js 
let req = pm.request.url.query.toObject ();
```
 5. Проверить, что **name в ответе равно name s request** (name забрать из request.)
``` js 
let name_request = req.name
let name = jsonData.name
pm.test("Name check", function () {
        pm.expect(name).to.eql(name_request);
});
```
 6. Проверить, что **age в ответе равно age s request** (age забрать из request.)
``` js 
let age_request = req.age
let age = jsonData.age
pm.test("Age check", function () {
        pm.expect(age).to.eql(age_request);
});
```
 7. Проверить, что **salary в ответе равно salary s request** (salary забрать из request.)
``` js 
let salary_request = req.salary
let salary = jsonData.salary
pm.test("Salary check2", function () {
        pm.expect(salary).to.eql(Number(salary_request));
});
```
 8. Вывести в консоль параметр **family из response**.
``` js 
let family = jsonData.family
console.log(family)
```
 9. Проверить, что у **параметра dog есть параметры name**.
``` js 
pm.test("Check dog_name", () => {
  pm.expect(jsonData.family.pets.dog).to.have.property("name");
});
```
 10. Проверить, что у **параметра dog есть параметры age**.
``` js 
pm.test("Check dog_age", () => {
  pm.expect(jsonData.family.pets.dog).to.have.property("age");
});
```
 11. Проверить, что **параметр name имеет значение Luky**.
``` js 
pm.test("Check dog_name_Luky", () => {
  pm.expect(jsonData.family.pets.dog.name).to.have.eql("Luky");
});
```
 12. Проверить, что **параметр age имеет значение 4**.
``` js 
pm.test("Check dog_age_4", () => {
  pm.expect(jsonData.family.pets.dog.age).to.have.eql(4);
});
```
---


## http:162.55.220.72:5005/object_info_4
 1. Отправить запрос.
 2. Статус **код 200**
``` js 
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```
 3. Спарсить **response body в json**
``` js 
let jsonData = pm.response.json();
```
 4. Спарсить **request**.
``` js 
let req = pm.request.url.query.toObject ();
```
 5. Проверить, что **name в ответе равно name s request** (name забрать из request.)
``` js 
let name_request = req.name
let name = jsonData.name
pm.test("Name check", function () {
        pm.expect(name).to.eql(name_request);
});
```
 6. Проверить, что **age в ответе равно age s request** (age забрать из request.)
``` js 
let age_request = req.age
let age = jsonData.age
pm.test("Age check", function () {
        pm.expect(age).to.eql(+(age_request));
});
```
 7. Вывести в консоль параметр **salary из request**.
``` js 
console.log(req.salary)
```
 8. Вывести в консоль параметр **salary из response**.
``` js 
console.log(jsonData.salary)
```
 9. Вывести в консоль **0-й элемент параметра salary из response**.
``` js 
console.log(jsonData.salary[0])
```
 10. Вывести в консоль **1-й элемент параметра salary параметр salary из response**.
``` js 
 console.log(jsonData.salary[1])
 ```
 11. Вывести в консоль **2-й элемент параметра salary параметр salary из response**.
``` js 
console.log(jsonData.salary[2])
```
 12. Проверить, что **0-й элемент параметра salary равен salary из request** (salary забрать из request.)
``` js 
let salary0 = req.salary
let salary = jsonData.salary[0]
pm.test("Salary check", function () {
        pm.expect(salary).to.eql(+(salary0));
});
```
 13. Проверить, что **1-й элемент параметра salary равен salary*2 из request** (salary забрать из request.)
``` js 
let salary1 = jsonData.salary[1]
pm.test("Salary1 check", function () {
        pm.expect(+(salary1)).to.eql(salary0*2);
});
```
 14. Проверить, что **2-й элемент параметра salary равен salary*3 из request** (salary забрать из request.)
``` js 
let salary2 = jsonData.salary[2]
pm.test("Salary2 check", function () {
        pm.expect(+(salary2)).to.eql(salary0*3);
});
```
 15. Создать в окружении переменную **name**
 16. Создать в окружении переменную **age**
 17. Создать в окружении переменную **salary**
 18. Передать в окружение переменную **name**
``` js 
pm.environment.set("name", name);
```
 19. Передать в окружение переменную **age**
``` js 
pm.environment.set("age", age);
```
 20. Передать в окружение переменную **salary**
``` js 
pm.environment.set("salary", salary);
```
 21. **Написать цикл который выведет в консоль по порядку элементы списка из параметра salary**.
``` js 
let salary_cycle = jsonData.salary
for (let i = 0; i < salary_cycle.length; i++) {
	console.log(salary_cycle[i]);
}
```
---


## http:162.55.220.72:5005/user_info_2
 1. Вставить параметр **salary из окружения в request**
 2. Вставить параметр **age из окружения в age**
 3. Вставить параметр **name из окружения в name**
 4. Отправить запрос.
 5. Статус **код 200**
``` js 
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```
 6. Спарсить response **body в json**.
``` js 
let jsonData = pm.response.json();
```
 7. Спарсить **request**.
``` js 
let req = request.data
```
 8. Проверить, что **json response имеет параметр start_qa_salary**
``` js 
pm.test("json response has start_qa_salary", () => {
  pm.expect(jsonData).to.have.property("start_qa_salary");
});
```
 9. Проверить, что **json response имеет параметр qa_salary_after_6_months**
``` js 
pm.test("json response has qa_salary_after_6_months", () => {
  pm.expect(jsonData).to.have.property("qa_salary_after_6_months");
});
```
 10. Проверить, что **json response имеет параметр qa_salary_after_12_months**
``` js 
pm.test("json response has qa_salary_after_12_months", () => {
  pm.expect(jsonData).to.have.property("qa_salary_after_12_months");
});
```
 11. Проверить, что **json response имеет параметр qa_salary_after_1.5_year**
``` js 
pm.test("json response has qa_salary_after_1.5_year", () => {
  pm.expect(jsonData).to.have.property("qa_salary_after_1.5_year");
});
```
 12. Проверить, что **json response имеет параметр qa_salary_after_3.5_years**
``` js 
pm.test("json response has qa_salary_after_3.5_years", () => {
  pm.expect(jsonData).to.have.property("qa_salary_after_3.5_years");
});
```
 13. Проверить, что **json response имеет параметр person**
``` js 
pm.test("json response has person", () => {
  pm.expect(jsonData).to.have.property("person");
});
```
 14. Проверить, что параметр **start_qa_salary равен salary из request** (salary забрать из request.)
``` js 
let salary_request = req.salary
let start_qa_salary = jsonData.start_qa_salary
pm.test("start_qa_salary check", function () {
        pm.expect(start_qa_salary).to.eql(+(salary_request));
});
```
 15. Проверить, что параметр **qa_salary_after_6_months равен salary*2 из request** (salary забрать из request.)
``` js 
let qa_salary_after_6_months = jsonData.qa_salary_after_6_months
pm.test("qa_salary_after_6_months check", function () {
        pm.expect(qa_salary_after_6_months).to.eql(+(salary_request)*2);
});
```
 16. Проверить, что параметр **qa_salary_after_12_months равен salary*2.7 из request** (salary забрать из request.)
``` js 
let qa_salary_after_12_months = jsonData.qa_salary_after_12_months
pm.test("qa_salary_after_12_months check", function () {
        pm.expect(qa_salary_after_12_months).to.eql(+(salary_request)*2.7);
});
```
 17. Проверить, что параметр **qa_salary_after_1.5_year равен salary*3.3 из request** (salary забрать из request.)
``` js
let qa_salary_after_1_5_year = jsonData['qa_salary_after_1.5_year']
pm.test("qa_salary_after_1.5_year check", function () {
        pm.expect(qa_salary_after_1_5_year).to.eql(+(salary_request)*3.3);
});
```
 18. Проверить, что параметр **qa_salary_after_3.5_years равен salary*3.8 из request** (salary забрать из request.)
``` js 
let qa_salary_after_3_5_years = jsonData['qa_salary_after_3.5_years']
pm.test("qa_salary_after_3.5_years check", function () {
        pm.expect(qa_salary_after_3_5_years).to.eql(+(salary_request)*3.8);
});
```
 19. Проверить, что в параметре **person, 1-й элемент из u_name равен salary из request** (salary забрать из request.)
``` js 
let name_salary = jsonData.person.u_name[1]
pm.test("u_name salary check", function () {
        pm.expect(name_salary).to.eql(+(salary_request));
});
```
 20. Проверить, что что параметр **u_age равен age из request** (age забрать из request.)
``` js 
let age = req.age
let u_age = jsonData.person.u_age
pm.test("u_age check", function () {
    pm.expect(u_age).to.eql(+(age));
pm.environment.get("variable_key");
});
```
 21. Проверить, что параметр **u_salary_5_years равен salary*4.2 из request** (salary забрать из request.)
``` js 
let u_salary_5_years = jsonData.person.u_salary_5_years
pm.test("u_salary_5_years check", function () {
        pm.expect(u_salary_5_years).to.eql(+(salary_request)*4.2);
});
```
 22. *** **Написать цикл который выведет в консоль по порядку элементы списка из параметра person**.
``` js 
for(let n in jsonData.person) {
    if(typeof(jsonData.person[n]) == "object"){
        console.log(n + ':')
        for(let i = 0; i < Object.keys(jsonData.person[n]).length; i++){
            console.log(jsonData.person[n][i]);
            }
 	}
  else {console.log(n + ' : ' + jsonData.person[n])}
}
```