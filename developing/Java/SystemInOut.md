public static void main(String[] args) {

		// input
		BufferedReader stdin = new BufferedReader(new InputStreamReader(
				System.in));

		// read
		String input = "";
		try {
			input = stdin.readLine();

		} catch (IOException e) {
			e.printStackTrace();
		}

		// ouput
		System.out.println(input);
	}
	
public static void main(String[] args) {

		// input
		Scanner sc = new Scanner(System.in);

		int n = sc.nextInt();
		for (int i = 1; i <= n; i++) {
			String string = sc.next();
		}

//		// ouput
//		for (Entry<String, Integer> entry : list) {
//			System.out.println(entry.getKey());
//		}
	}