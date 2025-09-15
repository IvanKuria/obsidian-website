
2025-01-07  14:12

Status: #child

Tags: #rust

# Iterating over a String

``` rust
fn main() {
	let sentence: String = String::from("my name is Ivan");
	let first_word: String = get_first_word(sentence);
	println!("{}", first_word);

}

fn get_first_word(sentence: String) -> String {

	let mut ans: String = String::new(); // initializes a new string: can also use String::from("")
	
	for char in sentence.chars() {
	
	// like for num in nums in python
	
	ans.push_str(char.to_string().as_str()); // adds to ans one char at a time
	
	if char == ' ' {
	
	break;
	
	};
	
	}
	
	return ans;
	
	}
```