--insert
create proc SP_Employee_Insert
@emp_id int,
@emp_name nvarchar(max),
@emp_type nvarchar(max),
@emp_contactNo nvarchar(max),
@emp_salary nvarchar(max),
@emp_address nvarchar(max)
as
begin
insert into employee_form (emp_id,emp_name,emp_type,emp_contatcNo,emp_salary,emp_address) values
(@emp_id,@emp_name,@emp_type,@emp_contatcNo,@emp_salary,@emp_address)
end

--To display all records
create proc SP_Employee_View
as
begin
select * from employee_form
end 

--update
create proc SP_Employee_Update
@emp_id int,
@emp_name nvarchar(max),
@emp_type nvarchar(max),
@emp_contactNo nvarchar(max),
@emp_salary nvarchar(max),
@emp_address nvarchar(max)
as
begin
Update employee_form set emp_name=@emp_name, emp_type=@emp_type, emp_contactNo=@emp_contactNo, emp_salary=@emp_salary, emp_address=@emp_address where emp_id=@emp_id
end


--delete
create proc SP_Employee_Delete
@emp_id int
as
begin
Delete employee_form where emp_id=@emp_id
end
