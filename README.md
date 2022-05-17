This is an educational repository that contains homeworks, completed as part of Vadim Ksendzov's training course on software testing. Here I am learning how to work in Postman. Below is my homework and solution

# HW_2 Postman


## http:162.55.220.72:5005/first
 1. Отправить запрос.
 2. Статус код 200
``` json 
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```
 3. Проверить, что в body приходит правильный string.
``` json 
pm.test("Body is the correct string", function () {
    pm.expect(pm.response.text()).to.include("This is the first responce from server!");
});
```
---

## http:162.55.220.72:5005/user_info_3
 1. Отправить запрос.
 2. Статус код 200
``` json 
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```
 3. Спарсить response body в json
``` json 
let resp = pm.response.json();
```
 4. Проверить, что name в ответе равно name s request (name вбить руками.)
``` json 
let name_s_request = 'Lena'
pm.test("Name check", function () {
        pm.expect(resp.name).to.eql(name_s_request);
});
```
 5. Проверить, что age в ответе равно age s request (age вбить руками.)
 ``` json 
let age_s_request = 30
pm.test("Age check", function () {
        pm.expect(+(resp.age)).to.eql(age_s_request);
});
```
 6. Проверить, что salary в ответе равно salary s request (salary вбить руками.)
 ``` json 
let salary_s_request = 1000
pm.test("Salary check", function () {
        pm.expect(resp.salary).to.eql(salary_s_request);
});
```
 7. Спарсить request.
 ``` json 
let req = request.data
```
 8. Проверить, что name в ответе равно name s request (name забрать из request.)
 ``` json 
pm.test("Name check2", function () {
        pm.expect(resp.name).to.eql(req.name);
});
```
 9. Проверить, что age в ответе равно age s request (age забрать из request.)
 ``` json 
pm.test("Age check2", function () {
        pm.expect(resp.age).to.eql(req.age);
});
```
 10. Проверить, что salary в ответе равно salary s request (salary забрать из request.)
``` json 
pm.test("Salary check2", function () {
        pm.expect(resp.salary).to.eql(+(req.salary));
});
```
 11. Вывести в консоль параметр family из response.
 ``` json 
console.log(resp.family)
```
 12. Проверить что u_salary_1_5_year в ответе равно salary*4 (salary забрать из request)
``` json 
pm.test("Salary_1_5_year check", function () {
        pm.expect(resp.family.u_salary_1_5_year).to.eql(req.salary * 4);
});
```

---

## http:162.55.220.72:5005/object_info_3
 1. Отправить запрос.
 2. Статус код 200
``` json 
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```
 3. Спарсить response body в json
``` json 
let resp = pm.response.json();
```
 4. Спарсить request.
``` json 
let req = pm.request.url.query.toObject ();
```
 5. Проверить, что name в ответе равно name s request (name забрать из request.)
``` json 
pm.test("Name check", function () {
        pm.expect(resp.name).to.eql(req.name);
});
```
 6. Проверить, что age в ответе равно age s request (age забрать из request.)
``` json 
pm.test("Age check", function () {
        pm.expect(resp.age).to.eql(req.age);
});
```
 7. Проверить, что salary в ответе равно salary s request (salary забрать из request.)
``` json 
pm.test("Salary check2", function () {
        pm.expect(resp.salary).to.eql(+(req.salary));
});
```
 8. Вывести в консоль параметр family из response.
``` json 
console.log(resp.family)
```
 9. Проверить, что у параметра dog есть параметры name.
``` json 
pm.test("Check dog_name", () => {
  pm.expect(resp.family.pets.dog).to.have.property("name");
});
```
 10. Проверить, что у параметра dog есть параметры age.
``` json 
pm.test("Check dog_age", () => {
  pm.expect(resp.family.pets.dog).to.have.property("age");
});
```
 11. Проверить, что параметр name имеет значение Luky.
``` json 
pm.test("Check dog_name_Luky", () => {
  pm.expect(resp.family.pets.dog.name).to.have.eql("Luky");
});
```
 12. Проверить, что параметр age имеет значение 4.
``` json 
pm.test("Check dog_age_4", () => {
  pm.expect(resp.family.pets.dog.age).to.have.eql(4);
});
```
---

## http:162.55.220.72:5005/object_info_4
 1. Отправить запрос.
 2. Статус код 200
``` json 
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```
 3. Спарсить response body в json
``` json 
let resp = pm.response.json();
```
 4. Спарсить request.
``` json 
let req = pm.request.url.query.toObject ();
```
 5. Проверить, что name в ответе равно name s request (name забрать из request.)
``` json 
pm.test("Name check", function () {
        pm.expect(resp.name).to.eql(req.name);
});
```
 6. Проверить, что age в ответе равно age s request (age забрать из request.)
``` json 
pm.test("Age check", function () {
        pm.expect(resp.age).to.eql(+(req.age));
});
```
 7. Вывести в консоль параметр salary из request.
``` json 
console.log(req.salary)
```
 8. Вывести в консоль параметр salary из response.
``` json 
console.log(resp.salary)
```
 9. Вывести в консоль 0-й элемент параметра salary из response.
``` json 
console.log(resp.salary[0])
```
 10. Вывести в консоль 1-й элемент параметра salary параметр salary из response.
``` json 
 console.log(resp.salary[1])
 ```
 11. Вывести в консоль 2-й элемент параметра salary параметр salary из response.
``` json 
console.log(resp.salary[2])
```
 12. Проверить, что 0-й элемент параметра salary равен salary из request (salary забрать из request.)
``` json 
pm.test("Salary check", function () {
        pm.expect(resp.salary[0]).to.eql(+(req.salary));
});
```
 13. Проверить, что 1-й элемент параметра salary равен salary*2 из request (salary забрать из request.)
``` json 
pm.test("Salary1 check", function () {
        pm.expect(+(resp.salary[1])).to.eql(req.salary * 2);
});
```
 14. Проверить, что 2-й элемент параметра salary равен salary*3 из request (salary забрать из request.)
``` json 
pm.test("Salary2 check", function () {
        pm.expect(+(resp.salary[2])).to.eql(req.salary * 3);
});
```
 15. Создать в окружении переменную name
 16. Создать в окружении переменную age
 17. Создать в окружении переменную salary
 18. Передать в окружение переменную name
``` json 
pm.environment.set("name", resp.name);
```
 19. Передать в окружение переменную age
``` json 
pm.environment.set("age", resp.age);
```
 20. Передать в окружение переменную salary
``` json 
pm.environment.set("salary", resp.salary[0]);
```
 21. Написать цикл который выведет в консоль по порядку элементы списка из параметра salary.
``` json 
let salary_cycle = resp.salary
for (let i = 0; i < salary_cycle.length; i++) {
	console.log(salary_cycle[i]);
}
```
---

## http:162.55.220.72:5005/user_info_2
 1. Вставить параметр salary из окружения в request
 2. Вставить параметр age из окружения в age
 3. Вставить параметр name из окружения в name
 4. Отправить запрос.
 5. Статус код 200
``` json 
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```
 6. Спарсить response body в json.
``` json 
let resp = pm.response.json();
```
 7. Спарсить request.
``` json 
let req = request.data
```
 8. Проверить, что json response имеет параметр start_qa_salary
``` json 
pm.test("json response has start_qa_salary", () => {
  pm.expect(resp).to.have.property("start_qa_salary");
});
```
 9. Проверить, что json response имеет параметр qa_salary_after_6_months
``` json 
pm.test("json response has qa_salary_after_6_months", () => {
  pm.expect(resp).to.have.property("qa_salary_after_6_months");
});
```
 10. Проверить, что json response имеет параметр qa_salary_after_12_months
``` json 
pm.test("json response has qa_salary_after_12_months", () => {
  pm.expect(resp).to.have.property("qa_salary_after_12_months");
});
```
 11. Проверить, что json response имеет параметр qa_salary_after_1.5_year
``` json 
pm.test("json response has qa_salary_after_1.5_year", () => {
  pm.expect(resp).to.have.property("qa_salary_after_1.5_year");
});
```
 12. Проверить, что json response имеет параметр qa_salary_after_3.5_years
``` json 
pm.test("json response has qa_salary_after_3.5_years", () => {
  pm.expect(resp).to.have.property("qa_salary_after_3.5_years");
});
```
 13. Проверить, что json response имеет параметр person
``` json 
pm.test("json response has person", () => {
  pm.expect(resp).to.have.property("person");
});
```
 14. Проверить, что параметр start_qa_salary равен salary из request (salary забрать из request.)
``` json 
pm.test("start_qa_salary check", function () {
        pm.expect(resp.start_qa_salary).to.eql(+(req.salary));
});
```
 15. Проверить, что параметр qa_salary_after_6_months равен salary*2 из request (salary забрать из request.)
``` json 
pm.test("qa_salary_after_6_months check", function () {
        pm.expect(resp.qa_salary_after_6_months).to.eql(+(req.salary)*2);
});
```
 16. Проверить, что параметр qa_salary_after_12_months равен salary*2.7 из request (salary забрать из request.)
``` json 
pm.test("qa_salary_after_12_months check", function () {
        pm.expect(resp.qa_salary_after_12_months).to.eql(+(req.salary)*2.7);
});
```
 17. Проверить, что параметр qa_salary_after_1.5_year равен salary*3.3 из request (salary забрать из request.)
``` json 
pm.test("qa_salary_after_1.5_year check", function () {
        pm.expect(resp['qa_salary_after_1.5_year']).to.eql(+(req.salary)*3.3);
});
```
 18. Проверить, что параметр qa_salary_after_3.5_years равен salary*3.8 из request (salary забрать из request.)
``` json 
pm.test("qa_salary_after_3.5_years check", function () {
        pm.expect(resp['qa_salary_after_3.5_years']).to.eql(+(req.salary)*3.8);
});
```
 19. Проверить, что в параметре person, 1-й элемент из u_name равен salary из request (salary забрать из request.)
``` json 
pm.test("u_name salary check", function () {
        pm.expect(resp.person.u_name[1]).to.eql(+(req.salary));
});
```
 20. Проверить, что что параметр u_age равен age из request (age забрать из request.)
``` json 
pm.test("u_age check", function () {
    pm.expect(resp.person.u_age).to.eql(+(req.age));
});
```
 21. Проверить, что параметр u_salary_5_years равен salary*4.2 из request (salary забрать из request.)
``` json 
pm.test("u_salary_5_years check", function () {
        pm.expect(resp.person.u_salary_5_years).to.eql(+(req.salary)*4.2);
});
```
 22. ***Написать цикл который выведет в консоль по порядку элементы списка из параметра person.
``` json 
for(let n in resp.person) {
    if(typeof(resp.person[n]) == "object"){
        console.log(n + ':')
        for(let i = 0; i < Object.keys(resp.person[n]).length; i++){
            console.log(resp.person[n][i]);
            }
 	}
  else {console.log(n + ' : ' + resp.person[n])}
}
```