# hello-world
just another repository
 //Quick Sort Method
    
    //this needs to be modified for this program
    
    //(Option 6) quick sort for population method."list" arbitrary for stateData 
    public static void quickSortPopulation(E element , int left, int right) {
    int left = head, right = tail;
        if (left < right) {
            int q = partitionPop(list, left, right);
            quickSortPopulation(list, left, q); //q becomes j returned from partition method
            quickSortPopulation(list, q + 1, right);
        }//end if statement
    }//end quickSort method

//(Part of Option 6) partition method  
    public static int partitionPop(StateInformation[] list, int left, int right) {

        int x = list[left].getPopulation(); //pivot need to sort by population
        int i = left - 1;                      //it is now an integer
        int j = right + 1;

        while (true) {

            j--;//this moves j to the rightmost end of the array
            while (list[j].getPopulation() > x) { //reverse logic
                j--; //j starts at right end + 1 spot and moves left until < pivot
            }

            i++; //this moves i to the leftmost end of the array (index 0)
            while (list[i].getPopulation() < x) {
                i++; //i starts at left end - 1 spot and moves right until > pivot
            }
            //once i and j are on a spot, it swaps their index locations
            if (i < j) { //swap if index # i < index # j
                StateInformation temp = list[j]; //data type is the object StateInformation
                list[j] = list[i];
                list[i] = temp;
            } else {
                return j; //returns the index of j which is the new pivot point
            }
        }//end while
    }//end partition method
    
