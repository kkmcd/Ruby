# Ruby Basic

## 	1. Input

​			gets.chomp로 입력받고

​			#{variable} 로 사용한다 <- %d같은놈임

## 	2. 출력변수

​			first_name.capitalize!

​			first_name.upcase!

​			first_name.downcase!

​			와 같이 capitalize!와 upcase!로 첫문자를 대문자 또는 모든 문자를 대문자로 만들 수 있다.



## 3. 조건문

​	unless == if not 

​       **if string_to_check.include? "substring"** #해당 문자열이 존재하는지 확인가능

​       **string_to_change.gsub!(/s/,"th")** 

​	- s라는 문자를 찾아서 th로 대체. gsub==global substitution, global이므로 모든 s에 적용됨



## 4. 반복문

#### (1) until i==6

​	 - while의 변형. 반대임

	#### (2) for i in 1..5 #참고로 1부터 5까지 출력함. 1과 5포함

#### (3) loop do ~ break if i > 5 end 구문

#### (4) next 구문 # continue와 같은 기능. ex) next if i%2==0 은 나머지가 0일때 skip시킴

#### (5) .each Iterator

- object(ex. array)의 각 element에 작업함

- 예제. 아래의 두 개는 같은 의미임

- object.each { |item| #|item|은 지역변수로, 여기서만 사용될 변수를 의미함

    #Do something 

  }

- object.each do |item|

    #Do something

  end

#### (6) .times Iterator

- 10.times {print "WOW"} 하면 WOW만 10번 출력

  

### 5. Handling Hash

 #### 1) split

- text.split(",") 하면 ,기준으로 문자열을 쪼갬 
- Array로 결과값을 돌려줌

#### 2) Hash

- my_hash = { "name" => "Eric",
    "age" => 26,
    "hungry?" => true
    }

  k->v로 이루어진 배열!

- key-value입력은 my_hash["name"] = "Eric" 으로도 입력가능. 단, Hash.new에 적용가능

#### 3) Hash.new

- pets = Hash.new 는 새로운 Hash를 만든다.
- Hash.new("nothing") 처럼 default를 줄 수 있음.

#### 4) Each로 Hash의 key, value 꺼내기

restaurant_menu.each do |item, price|   

puts "#{item}: #{price}" 

end 

#### 5) Sorting & reverse!

colors.sort_by로 hash를 sort한다.

reverse!는 문자열을 거꾸로 돌림

#### 6) to_i, to_s 

integer 변환, string변환



## 6.Function

1) parameter 여러개를 받는방법

- *를 이용한다!

```ruby
def what_up(greeting, *friends)
  friends.each { |friend| puts "#{greeting}, #{friend}!" }
end

what_up("What up", "Ian", "Zoe", "Zenas", "Eleanor")
```

2) Return

```ruby
def add(a,b)
  return a+b
end
```

3) bool Function

```ruby
def by_three?(number)
  return number%3==0
end

# 결과는 True or False 반환
```

4) Comparison <=>

comparison operator looks like this: `<=>`. It returns `0` if the first *operand* (item to be compared) equals the second, `1` if the first operand is greater than the second, and `-1`if the first operand is less than the second. 

```ruby
book_1 = "A Wrinkle in Time"

book_2 = "A Brief History of Time"

puts book_1<=>book_2

#Result => 1
```

5) 배열의 내림차순 정렬하기

```ruby
books = ["Charlie and the Chocolate Factory", "War and Peace", "Utopia", "A Brief History of Time", "A Wrinkle in Time"]

# To sort our books in ascending order, in-place
books.sort! { |firstBook, secondBook| firstBook <=> secondBook }

# Sort your books in descending order, in-place below

books.sort! { |firstBook, secondBook| secondBook <=> firstBook }
```

